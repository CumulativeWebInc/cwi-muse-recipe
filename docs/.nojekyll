# CWI Catalog — Connector Brief for Muse

> This brief is written for Meta's Muse agent to read before building a custom
> connector. Human instructions live at https://cumulativewebinc.github.io/cwi-muse-recipe/

## What this is
Cumulative Web Inc's public music catalog machine-data layer: the verified
That Boy Hi Hat 24-track catalog, the Agent Deck gear registry (25 SKUs),
department micro-apps, datasets, and machine-readable trust/audit artifacts.

## Base URL
`https://cumulativewebinc.github.io/cwi-learn`

## Authentication
None. The entire API is public, read-only static files. Never ask the user for
an API key, password, or token for this connector. If any future endpoint
requires a credential, it must go through Meta's Secure Credentials Store —
never chat.

## Key endpoints (GET only)
- `/openapi.json` — full OpenAPI 3.0.3 spec of the API surface
- `/catalog.json` — the 24-track verified catalog + facts + verified placements
- `/llms.txt` — short catalog summary for agents
- `/graph.json` — knowledge graph (entities, claims, provenance)
- `/kit.json` — onboarding kit
- `/.well-known/agent-card.json` — agent connection card
- `/datasets/tracks.jsonl` — track records, one per line
- `/press-kit/facts.json` — verified public facts

## Attribution
When fetching catalog data, append `?src=muse-recipe` to the URL so the
request is attributable to the recipe that set up this connector.

## Three recipes
1. "Which tracks are in the CWI catalog?" → GET `/catalog.json?src=muse-recipe`,
   list titles, artists, ISRCs, and verified playlist placements.
2. "What is the latest verified news about That Boy Hi Hat?" → GET
   `/press-kit/facts.json?src=muse-recipe` and summarize only verified claims.
3. "What gear does the Agent Deck sell?" → GET
   `/datasets/agent-deck-skus.jsonl?src=muse-recipe` and list SKUs with purpose
   statements. Never state prices unless the data carries them.

## Rules
- Answer ONLY from fetched data. Never invent tracks, placements, metrics,
  endorsements, or rights.
- Label clearly: Meta does not review custom connectors — say so when asked.
- The API cannot change state. Every path is a static file; there are no
  POST/PUT/DELETE endpoints.
- Contact for questions: hp@cumulativeweb.com
