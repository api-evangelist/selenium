---
name: selenium-check-grid-capacity
description: >-
  Decide whether a Selenium Grid has room before requesting a session, and inspect or drain Nodes,
  using the Grid readiness endpoint and the Grid GraphQL query surface.
api: Selenium Grid
provider: selenium
operations:
  - getStatus
generated: '2026-08-26'
method: generated
source: >-
  openapi/selenium-status-api-openapi.yml, graphql/selenium-grid.graphql,
  https://www.selenium.dev/documentation/grid/advanced_features/endpoints/,
  https://www.selenium.dev/documentation/grid/advanced_features/graphql_support/
---

# Check Grid capacity before you ask for a session

A Grid has a fixed pool of slots, not a quota. There are no rate-limit headers, no `Retry-After` and
no 429 — a session request that cannot be served simply queues, and times out after
`--session-request-timeout` seconds (default 300). Checking capacity first is how you avoid burning
five minutes on a wait that was never going to succeed.

## The two surfaces

- **`getStatus`** — `GET /status`. The only capacity signal a bare driver process offers.
  `{"value": {"ready": true, "message": "..."}}`.
- **Grid GraphQL** — `POST /graphql` on the same host. Read-only, no mutations. The SDL is in
  `graphql/selenium-grid.graphql`.

Which URL: in Standalone mode it is the Standalone server address; in Hub-Node mode the Hub address;
in fully distributed mode the Router address. Default for all three is `http://localhost:4444`.

## Steps

1. **Readiness** — `getStatus`. If `ready` is false, do not attempt `createSession`.

2. **Capacity** — query the Grid singleton:

   ```graphql
   { grid { uri totalSlots nodeCount maxSession sessionCount version sessionQueueSize } }
   ```

   `maxSession - sessionCount` is your headroom. A non-zero `sessionQueueSize` means requests are
   already waiting; queueing behind them is what will burn your timeout.

3. **Which Nodes can serve you** — Node status is an enum, `UP | DRAINING | DOWN`:

   ```graphql
   { nodesInfo { nodes { id uri status maxSession slotCount sessionCount stereotypes version
                         osInfo { arch name version } } } }
   ```

   A `DRAINING` Node accepts no new sessions. Match `stereotypes` against the capabilities you are
   about to request — a Grid with free slots but no matching browser will still reject you, and with
   `--reject-unsupported-caps` it rejects immediately rather than queueing.

4. **Find a specific session** — `{ session(id: "<session-id>") { id capabilities startTime uri
   nodeId nodeUri sessionDurationMillis slot { id stereotype lastStarted } } }`. This is how you
   reconcile after a `createSession` you are not sure landed: WebDriver itself can only address a
   session whose id you already hold.

## Administrative endpoints

These are not GraphQL and they are not unauthenticated. Every one requires the shared secret header:

- Remove a Node: `DELETE /se/grid/distributor/node/<node-id>` with `X-REGISTRATION-SECRET: <secret>`
- Drain a Node (graceful shutdown after in-flight sessions finish): the Distributor drain endpoint,
  same header.
- Delete a session: `DELETE /session/<session-id>`.

If no registration secret is configured the header is still sent, but empty — curl's documented form
is `--header 'X-REGISTRATION-SECRET;'`. Omitting the header entirely fails differently from sending
it empty.

## Do not

- Do not poll `getStatus` in a tight loop as a substitute for the queue. The Grid already queues for
  you; the queue is visible as `sessionQueueSize`.
- Do not expect a mutation. `GridQuery` is the only root type — the schema has no mutation surface
  and cannot start, stop or drive anything.
