---
name: selenium-read-page-state
description: >-
  Read-only extraction from a live page — current URL, title, all matching elements and the
  browsing context's cookies — without taking any irreversible action.
api: Selenium WebDriver
provider: selenium
operations:
  - createSession
  - navigateTo
  - getCurrentUrl
  - getTitle
  - findElements
  - getCookies
  - deleteSession
generated: '2026-08-26'
method: generated
source: >-
  openapi/selenium-navigation-api-openapi.yml, openapi/selenium-elements-api-openapi.yml,
  openapi/selenium-cookies-api-openapi.yml, conventions/selenium-conventions.yml
---

# Read page state

Everything in this skill except `createSession`, `navigateTo` and `deleteSession` is a read. Use it
when you need to observe a page and must not change it.

## Steps

1. `createSession` — `POST /session` with `{"capabilities": {"alwaysMatch": {"browserName": "chrome"}}}`.
2. `navigateTo` — `POST /session/{sessionId}/url`. This is a write in the sense that it moves the
   browsing context, but it is reversible with `navigateBack` for as long as the history entry lives.
3. `getCurrentUrl` — `GET /session/{sessionId}/url`. Returns `{"value": "https://..."}`. Compare it
   against the URL you requested to detect a redirect or an interstitial.
4. `getTitle` — `GET /session/{sessionId}/title`.
5. `findElements` — `POST /session/{sessionId}/elements` with `{"using": "...", "value": "..."}`.
   Returns the **whole** match set; there is no pagination anywhere in this protocol. An empty array
   is a valid answer and is *not* an error — `no such element` is returned by `findElement`
   (singular), not by `findElements`.
6. `getCookies` — `GET /session/{sessionId}/cookie`. Returns every cookie associated with the
   current browsing context's active document.
7. `deleteSession` — `DELETE /session/{sessionId}`. Always.

## Cautions

- **`findElement`/`findElements` are reads, but time-dependent reads.** The same call a second later
  can return a different reference set. If you need a stable view, capture what you need in one pass.
- **Element references are opaque handles, not selectors.** They break on re-render
  (`stale element reference`). Do not persist them beyond the session, and do not treat them as ids.
- **Cookies are session data.** `getCookies` can return authentication cookies for whatever is logged
  in. Treat the response as a secret: do not log it, do not put it in an artifact, do not pass it on.
- **Do not reach for `executeScriptSync` to make this easier.** It runs arbitrary JavaScript with the
  page's own privileges and can issue authenticated requests as the logged-in user. It is the one
  operation in this surface classified safety-critical in `agentic-access/selenium-agentic-access.yml`.
