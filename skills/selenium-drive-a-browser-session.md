---
name: selenium-drive-a-browser-session
description: >-
  Open a W3C WebDriver session against a Selenium remote end, navigate to a page, locate an element
  and click it, then always tear the session down. The baseline agent flow for browser automation.
api: Selenium WebDriver
provider: selenium
operations:
  - createSession
  - navigateTo
  - findElement
  - clickElement
  - getCurrentUrl
  - deleteSession
generated: '2026-08-26'
method: generated
source: >-
  openapi/selenium-session-api-openapi.yml, openapi/selenium-navigation-api-openapi.yml,
  openapi/selenium-elements-api-openapi.yml, conventions/selenium-conventions.yml,
  errors/selenium-problem-types.yml
---

# Drive a browser session

## Before you start

There is **no Selenium-operated host**. You need a remote end you control — a driver process
(chromedriver on 9515, geckodriver on 4444) or a Selenium Grid. The documented default base is
`http://localhost:4444`. If you do not have one running, this skill has nothing to call.

Read `conventions/selenium-conventions.yml` first if you are about to act on a production site.
`clickElement` and `executeScriptSync` are **not reversible** — their effects land in the
application under test, and Selenium has no undo.

## Steps

1. **Check the remote end is up** — `getStatus` (`GET /status`). The response is
   `{"value": {"ready": true, "message": "..."}}`. If `ready` is false, stop; creating a session
   will fail with `session not created`.

2. **Create the session** — `createSession` (`POST /session`) with a W3C capabilities request:

   ```json
   {"capabilities": {"alwaysMatch": {"browserName": "chrome"}}}
   ```

   Keep the returned session id. **This is not idempotent.** If the call times out, do not retry
   blindly — a retry that succeeds while the first attempt also succeeded leaks a browser process
   and a Grid slot. Reconcile by listing sessions on the Grid GraphQL surface instead.

3. **Navigate** — `navigateTo` (`POST /session/{sessionId}/url`) with `{"url": "https://..."}`.

4. **Locate the element** — `findElement` (`POST /session/{sessionId}/element`) with a W3C locator
   `{"using": "css selector", "value": "#submit"}`. You get back an **opaque element reference**,
   not a selector. It is valid only while that DOM node stays attached.

5. **Wait rather than retry.** Selenium's own guidance is explicit: prefer explicit waits over fixed
   sleeps, and never mix implicit and explicit waits. If `findElement` returns `no such element`,
   the element usually is not in the DOM *yet* — poll `findElement` on a deadline. Do not paper over
   it with a sleep.

6. **Click** — `clickElement` (`POST /session/{sessionId}/element/{elementId}/click`). Irreversible.

7. **Confirm by reading state, not by re-sending** — `getCurrentUrl`
   (`GET /session/{sessionId}/url`) or `getTitle`. This protocol has no idempotency key and no
   request de-duplication; reading is how you find out whether a write landed.

8. **Always tear down** — `deleteSession` (`DELETE /session/{sessionId}`) in a finally block. It
   terminates the session, quits the driver and frees the slot. A leaked session holds a real
   browser process until the Node's `--session-timeout` (default 300s) kills it.

## Errors you will actually hit

Branch on `value.error`, never on `value.message` or the HTTP status alone — several distinct codes
share 404.

| `value.error` | Status | What to do |
|---|---|---|
| `no such element` | 404 | Wrong place, wrong time, or a changed locator. Wait and re-locate. |
| `stale element reference` | 404 | The page re-rendered. Re-run `findElement`; never cache references across navigation. |
| `element click intercepted` | 400 | Something is overlaying the target. Wait for it to clear or scroll into view. |
| `element not interactable` | 400 | Wait on an interactability condition. |
| `invalid session id` | 404 | The session is gone — timed out or already deleted. Start a new one. |
| `invalid selector` | 400 | The CSS/XPath is malformed, or a CSS value was passed as XPath. |
| `session not created` | 500 | Historically a driver/browser version mismatch. Let Selenium Manager resolve the driver; do not set driver paths. |

Full registry: `errors/selenium-problem-types.yml`.

## Do not

- Do not set driver executable paths or use third-party driver managers. Selenium Manager has
  shipped with every release since 4.6 and resolves drivers itself.
- Do not use Desired Capabilities — removed in Selenium 4. Use per-browser Options.
- Do not expose a remote end beyond localhost without `--username`/`--password` and
  `--registration-secret`. An unauthenticated WebDriver port is remote code execution in a browser.
