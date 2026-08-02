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

Status is the issue state. Open means planned or in progress; closed means shipped or dropped,
and the closing comment says which.

## The three planning surfaces

They do not overlap, and which one a thing belongs on is usually obvious once you know the split.

| Surface | Covers | Where |
|---|---|---|
| **APIs.io road map** | APIs.io itself — search, the site, the rating, the add-an-API pipeline | [apis.io/roadmap](https://apis.io/roadmap/) |
| **Production queue** | The research line that publishes on a cadence — Industry and Standard Reports, Insights Bundles, Leader Shorts | [papers.apievangelist.com/queue](https://papers.apievangelist.com/queue/) |
| **This road map** | Everything else across the network, and anything that does not fit the other two | you are here |

The queue answers "what publishes next" and runs on its own order. This repo answers "what should
we build or fix next" and does not.

## Where this is not the right place

- **Asking us to change your listing** — add, rescore, correct, or delist your API in the
  [APIs.io Inbox](https://github.com/api-search/inbox), or on your own provider repo.
- **Something specific to one provider's profile** — open it on that provider's repo under
  [api-evangelist](https://github.com/orgs/api-evangelist/repositories).
- **APIs.io site and search direction** — the public [APIs.io roadmap](https://apis.io/roadmap/)
  is the reader-facing view; the work behind it gets tracked here.

## Weighing in

Open an issue. Suggestions about what to prioritize are as welcome as bug reports — a lot of what
ends up here started as someone pointing out something that was not working.
