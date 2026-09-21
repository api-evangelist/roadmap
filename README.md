```markdown
# API Evangelist Road Map

Where work across the API Evangelist network gets aggregated and tracked in the open.

API Evangelist spans a lot of surfaces — the catalog of provider profiles under
[api-evangelist](https://github.com/orgs/api-evangelist/repositories), [APIs.io](https://apis.io)
and its search and rating, the [Kin Score](https://apis.io/rating/), the research and reports, and
the governance tooling. Work on any of it used to live wherever it happened to start. This repo is
the single place it gets written down.

## How it works

**Every work item is an issue**, labeled by area. Issues link out to the repo where the work
actually lands — a provider repo, `api-search/network`, wherever — so this stays an index rather
than a second copy of the truth.

| Label | Covers |
|---|---|
| `area:catalog` | Provider profiles, artifacts, enrichment, data quality |
| `area:apis-io` | APIs.io search, the site, the add-an-API pipeline |
| `area:scoring` | The Kin Score rubric, Agent Readiness, provenance |
| `area:support` | How people reach us and how requests get handled |
| `area:research` | Reports, papers, and the analysis behind them |
| `area:tooling` | Governance tools, MCP servers, developer surfaces |
| `rubric` | Changes the Kin Score rubric itself. **Frozen between releases** — see below |
| `score-moving` | Does not change the rubric, but moves published scores. Work anytime; publishes on a release date |

Status is the issue state. Open means planned or in progress; closed means shipped or dropped,
and the closing comment says which.

## Security Notice / Active Hardening: OAuth DCR & Redirect URI Validation

Following responsible disclosure (Mamun Khanka, 2026-09-21), we are hardening our OAuth Dynamic Client Registration (DCR) pipeline. 

**Design Decision:** Keyless DCR per RFC 7591 remains **open** to support seamless MCP agent self-registration. Requiring initial access tokens or manual approval breaks agent onboarding and will not be adopted. Instead, we are implementing the following mitigations:
- **Scope & Severity Audit:** Confirm what OAuth-authorized clients can access (scopes to data) to establish exact threat severity.
- **Strict Redirect URI Enforcement:** Constrain and validate `redirect_uri` at `/authorize` (exact-match against the client's registered set; rejecting open redirects).
- **Unverified Client Consent:** Update the consent screen to explicitly flag dynamically-registered clients as **unverified** (preventing name-spoofing first-party confusion).
- **Reporter Liaison:** Acknowledge, credit, and communicate our hardening path while preserving intentional MCP open DCR design.

## The Kin Score release freeze

**The Kin Score ships on dates, not when a change happens to be ready.** As of **0.22.0
(2026-09-13)** the rubric is frozen, and the next three releases are pinned to the fall
conference run:

| Milestone | Date | Event | Expected |
|---|---|---|---|
| [Kin Score — London](https://github.com/api-evangelist/roadmap/milestone/1) | 2026-09-30 | API Days London, 30 Sep – 1 Oct | 0.23.0 |
| [Kin Score — Stockholm](https://github.com/api-evangelist/roadmap/milestone/2) | 2026-10-13 | Nordic APIs Platform Summit, 12–14 Oct | 0.24.0 |
| [Kin Score — Paris](https://github.com/api-evangelist/roadmap/milestone/3) | 2026-12-01 | FOST / API Days Paris, 1–3 Dec | 0.25.0 |

The FOST / API Days **Australia** session (Melbourne, 28 October, remote) sits between Stockholm
and Paris and **runs on the Stockholm release** — it is a session, not a release.

### Why

A rating people are asked to act on has to be predictable enough to act on. If the rubric moves
whenever a change lands, a provider who does the work has no way to know which version graded
them, and "your score went up" is not a sentence anyone can plan around. Publishing on announced
dates gives providers a window to prepare — *you have three weeks, here is what changes, update
your listing and be part of the release* — and it gives each release somewhere to be explained
out loud.

### What this means for an issue

- **`rubric` — do not work it between releases.** New checks, changed checks, re-weighted facets,
  re-cut bands, new layers. These queue against a milestone and ship on that date.
- **`score-moving` — work it anytime, publish on a release date.** Harvest gaps, stale artifacts,
  a check that reads the wrong thing. The rubric is unchanged, but published numbers move, so
  providers still deserve the same warning.
- **`bug` with no score impact — work it anytime, ship it anytime.** The freeze protects the
  published rating, not the repo.

A bug that happens to be in scoring code is still a bug. The test is not *which file does this
touch* but *does a provider's published number change, and would they be surprised by it*.

## The three planning surfaces

They do not overlap, and which one a thing belongs on is usually obvious once you know the split.

| Surface | Covers | Where |
|---|---|---|
| **APIs.io road map** | APIs.io itself — search, the site, the rating, the add-an-API pipeline |