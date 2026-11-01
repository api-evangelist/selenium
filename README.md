# Selenium

<!-- API-EVANGELIST-PROVENANCE:BEGIN -->
> ### About this repository
>
> **This is not our API.** This repository is an independent, third-party profile of a company's
> **publicly available** API surface, maintained by [API Evangelist](https://apievangelist.com).
> API Evangelist does not operate, host, resell, or support this company's APIs, and is not
> affiliated with or endorsed by the company unless stated on the profile.
>
> **Where the information came from.** Everything here is assembled from material a member of the
> public can reach with a browser and no credentials — the company's own website, developer portal
> and documentation, the specifications it publishes for public use (OpenAPI, AsyncAPI, JSON Schema,
> `apis.json`, `llms.txt` and similar), its public repositories, and its public status, pricing and
> changelog pages. **Nothing here is obtained by breaching a system, defeating an access control, or
> using credentials of any kind.**
>
> **The rating is an independent assessment.** The Kin Score and Agent Readiness rating are
> independently calculated scores of a company's *public* API artifacts, produced by API Evangelist
> against a published rubric. They are not certifications, endorsements, security assessments, or
> audits, and they score published artifacts — not the quality, safety, or security of the software.
>
> **Corrections, re-scores, and removal are free.** No partnership, contract, or purchase is
> required, and you do not need to justify the request.
>
> - **Something wrong?** Open an issue on this repository, or email
>   [info@apievangelist.com](mailto:info@apievangelist.com).
> - **Published something new?** Ask for a re-score and we will re-run the rating.
> - **Want the listing taken down?** Say so and we will honor it. The profile is reduced to your
>   company name, a factual description, and a link to your own site, and the company is recorded as
>   **unrated** — never scored zero for having asked.
>
> **Response times.** Acknowledgement within **one business day**; removal or restriction within
> **two business days**; corrections and re-scores within **five business days**.
>
> **Not from the company, and here with a question?** You are welcome here — we would rather be the
> front line and point you the right way than have a good report go nowhere. What this repository
> can answer is narrow, though, so it is worth knowing who you are actually looking for:
>
> - **A question about how the API works, an account, billing, or a bug in the service** — that is
>   the company's own support, not us. We profile this API; we do not operate it and cannot see
>   your account.
> - **A bug in an open-source project we only catalog** — file it on that project's own repository.
>   This has happened with a real and correct bug report that reached us instead of the people who
>   could fix it, which helped nobody.
> - **Anything about this listing itself** — the description, the tags, the rating, a missing or
>   wrong artifact — is ours. Open an issue here.
> - **Not sure, or something general about API Evangelist or APIs.io** — open an issue on the
>   [APIs.io Inbox](https://github.com/api-search/inbox) and we will route it.
>
> **This repository contains no software, and we will never ask you to download anything.** There is
> no build, release, installer, or binary here — only text and machine-readable API descriptions, so
> there is nothing here that can be "corrupt" or need "repairing". Any issue, comment, or email
> claiming otherwise and offering a download link is not from us and is hostile. Do not follow the
> link; it is a lure. Report it to GitHub and, if you like, tell us at
> [info@apievangelist.com](mailto:info@apievangelist.com) so we can take it down.
>
> **On a security or compliance team?** Email
> [info@apievangelist.com](mailto:info@apievangelist.com) with *security* in the subject line and
> you will get a person, not a form. We will tell you exactly which public URLs this profile was
> built from so your team can see the same surface we did, and we will take the listing down on
> request while you work through it.
>
> Full detail: **[Where this data comes from](https://apievangelist.com/about/where-our-data-comes-from)**
<!-- API-EVANGELIST-PROVENANCE:END -->

Selenium is the open-source browser automation project behind the W3C WebDriver and WebDriver BiDi standards. It drives real browsers through a vendor-neutral, standardised HTTP wire protocol that the browser vendors implement themselves, with official language bindings for Java, Python, C#, Ruby and JavaScript, all released in lockstep. The suite covers WebDriver (the browser-control protocol), Selenium Grid (distributed, parallel execution across machines and platforms), Selenium Manager (a Rust CLI that resolves and downloads matching browser drivers automatically) and Selenium IDE (record and playback). Selenium is self-hosted software rather than a service: there is no vendor-operated API host, no account and no pricing — the remote end runs on infrastructure the consumer owns, at a documented default of http://localhost:4444, under Apache-2.0 and the stewardship of the Software Freedom Conservancy.

**Areas:** Automation · Browser · End-to-End Testing · Quality Assurance · Testing · WebDriver

## Selenium on APIs.io

Everything profiled for Selenium is published on APIs.io rather than in this repository. Start at the provider page — **[apis.io/providers/selenium/](https://apis.io/providers/selenium/)** — or go straight to one of the APIs or properties below.

### APIs (8)

- [Selenium WebDriver](https://apis.io/apis/selenium/selenium-webdriver/) — WebDriver is a browser automation framework that accepts commands and sends them to a browser. It is implemented through a browser-specific driver that…
- [Selenium Grid](https://apis.io/apis/selenium/selenium-grid/) — Selenium Grid allows you to run test cases in different machines across different platforms. It enables the execution of test scripts on remote machines by…
- [Selenium Cookies API](https://apis.io/apis/selenium/selenium-cookies-api/) — Cookie management
- [Selenium Elements API](https://apis.io/apis/selenium/selenium-elements-api/) — Element discovery and interaction
- [Selenium Navigation API](https://apis.io/apis/selenium/selenium-navigation-api/) — Page navigation and metadata
- [Selenium Script API](https://apis.io/apis/selenium/selenium-script-api/) — Execute JavaScript in the page context
- [Selenium Session API](https://apis.io/apis/selenium/selenium-session-api/) — Session lifecycle
- [Selenium Status API](https://apis.io/apis/selenium/selenium-status-api/) — Remote end readiness

### Published properties

Each property below is a page on APIs.io carrying the machine-readable artifact and what it says.

#### AsyncAPI (1)

Event-driven and webhook contracts.

- [Selenium Bidi Events](https://apis.io/asyncapis/selenium/selenium-bidi-events/)

#### MCP servers (1)

Model Context Protocol servers that expose the API to agents.

- [Selenium WebDriver (candidate MCP surface)](https://apis.io/servers/selenium/selenium-webdriver-candidate-mcp-surface/)

#### Agentic access (1)

Which operations an agent can call, which act, and which need a human in the loop.

- [Selenium Agentic Access](https://apis.io/agentic-access/selenium/selenium-agentic-access/)

#### Collections (7)

Postman and Open Collection request collections.

- [Selenium WebDriver (W3C Wire Protocol)](https://apis.io/collections/selenium/open-selenium/)
- [Selenium WebDriver (W3C Wire Protocol) Cookies API](https://apis.io/collections/selenium/open-selenium-cookies-api/)
- [Selenium WebDriver (W3C Wire Protocol) Cookies Elements API](https://apis.io/collections/selenium/open-selenium-elements-api/)
- [Selenium WebDriver (W3C Wire Protocol) Cookies Navigation API](https://apis.io/collections/selenium/open-selenium-navigation-api/)
- [Selenium WebDriver (W3C Wire Protocol) Cookies Script API](https://apis.io/collections/selenium/open-selenium-script-api/)
- [Selenium WebDriver (W3C Wire Protocol) Cookies Session API](https://apis.io/collections/selenium/open-selenium-session-api/)
- [Selenium WebDriver (W3C Wire Protocol) Cookies Status API](https://apis.io/collections/selenium/open-selenium-status-api/)

#### Overlays (6)

OpenAPI overlays, including conversational phrasing for each operation.

- [Selenium Cookies Api Overlay](https://apis.io/overlays/selenium/selenium-cookies-api-overlay/)
- [Selenium Elements Api Overlay](https://apis.io/overlays/selenium/selenium-elements-api-overlay/)
- [Selenium Navigation Api Overlay](https://apis.io/overlays/selenium/selenium-navigation-api-overlay/)
- [Selenium Script Api Overlay](https://apis.io/overlays/selenium/selenium-script-api-overlay/)
- [Selenium Session Api Overlay](https://apis.io/overlays/selenium/selenium-session-api-overlay/)
- [Selenium Status Api Overlay](https://apis.io/overlays/selenium/selenium-status-api-overlay/)

#### Security (2)

Authentication, trust centre, and vulnerability disclosure.

- [Selenium Authentication](https://apis.io/security/selenium/selenium-authentication/)
- [Selenium Domain Security](https://apis.io/security/selenium/selenium-domain-security/)

#### Plans and pricing (1)

Published plans, tiers and prices.

- [Selenium Plans Pricing](https://apis.io/plans/selenium/selenium-plans-pricing/)

#### Rate limits (1)

Published request limits.

- [Selenium Rate Limits](https://apis.io/rate-limits/selenium/selenium-rate-limits/)

#### FinOps (1)

What the API costs to run, by operation.

- [Selenium Finops](https://apis.io/finops/selenium/selenium-finops/)

## Where to find this API

Links to the company's own pages. This repository publishes no copy of their specifications — the canonical document is theirs and lives at the URLs below.

- [Website](https://www.selenium.dev/)
- [Documentation](https://www.selenium.dev/documentation/)
- [Getting started](https://www.selenium.dev/documentation/webdriver/getting_started/)
- [API reference](https://www.selenium.dev/selenium/docs/api/java/)
- [Support](https://www.selenium.dev/support/)
- [Blog](https://www.selenium.dev/blog/)
- [GitHub](https://github.com/SeleniumHQ)

## API Evangelist rating

**Kin Score 38.1** — thin · rubric 0.24.0 · scored 2026-10-17

| Facet | Score |
|---|---|
| Discoverability | 71.4 |
| Contract quality | 44.7 |
| Contract governance | 18.2 |
| Operational transparency | 26.3 |
| Developer ergonomics | 73.2 |
| Access clarity | 0.0 |

**Agent readiness 27.9** — agent-aware

| Agent-readiness dimension | Result |
|---|---|
| Spec Presence | yes |
| Agentic Access | derived (partial credit) |
| Reversibility Documented | — |
| MCP Server | — |
| Auth Clarity | bearer (partial credit) |
| Idempotency | — |
| Error Semantics | documented (partial credit) |
| OpenAPI Examples | — |
| Rate Limit Signal | documented (partial credit) |
| Event Surface Described | yes |
| Agent Skills | derived (partial credit) |
| Well Known Catalog | — |
| Consent Identity | — |
| Agent Card | — |
| Dry Run Mode | — |
| Delegated Identity | — |
| Protected Resource Metadata | — |
| Dynamic Client Registration | — |
| Agentic Commerce | — |

**Regulatory alignment 16.7** — Horizontal (data, software, accessibility, platform)

The rubric is published at [github.com/api-evangelist/kin-score](https://github.com/api-evangelist/kin-score). The per-check breakdown behind these numbers — which checks were earned, partial or missed — along with score history and how this provider compares to its peers, is available at [apis.io/providers/selenium/](https://apis.io/providers/selenium/).

## How this profile is made

API Evangelist profiles a company's public API surface the way a developer would find it: the website, developer portal and documentation, the specifications it publishes, its public repositories, and its pricing, status and changelog pages. From that it derives the properties above — contracts split per API, workflows, schemas, collections, governance rules, plans and rate limits — and scores them against the published [Kin Score rubric](https://github.com/api-evangelist/kin-score).

The artifacts are published on [APIs.io](https://apis.io), not in this repository. This repository is the public record for Selenium: the place to say something is wrong, missing or out of date, and to ask for a re-score or a removal.

## Open an issue

- **Something about this listing** — a wrong description, a missing API, a stale artifact or a question about the rating: [open an issue on this repository](https://github.com/api-evangelist/selenium/issues/new).
- **A new API, or one that is not in the catalog yet** — [submit it on APIs.io](https://apis.io/add/).
- **Anything else** — [the APIs.io inbox](https://github.com/api-search/inbox/issues/new) or [info@apievangelist.com](mailto:info@apievangelist.com).
