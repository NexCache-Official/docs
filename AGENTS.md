# AdeHQ documentation

Internal and product documentation for [AdeHQ](https://ade-hq-eight.vercel.app), built on [Mintlify](https://mintlify.com).

## Repository structure

| Tab | Audience | Contents |
|-----|----------|----------|
| **Documentation** | Product users | Quickstart, concepts, guides, account, FAQ |
| **Developer** | Engineering team | Architecture, PRDs, platform internals, changelog |
| **API reference** | Engineering team | All route handlers, auth, request/response shapes |
| **Database** | Engineering team | Postgres schema, migrations |
| **Development** | Engineering team | Local setup, env vars, debugging, integrations |

Source code: [NexCache-Official/AdeHQ](https://github.com/NexCache-Official/AdeHQ) (currently **v17.0.0**).

## Terminology

- **Workspace** — tenant boundary (not "project" or "organization")
- **AI employee** — configured agent with role, model tier, and permissions (not "bot" or "assistant")
- **Channel** — group project room (`kind: channel`)
- **Direct message (DM)** — 1:1 room with an AI employee (`kind: dm`)
- **Topic** — thread inside a room (Messaging v2)
- **Agent run** — queued or executing AI response job
- **Collaboration plan** — multi-employee orchestration config (V16.9)
- **Work graph** — tasks, memory, approvals, and work log linked to agent runs

## Style

- Second person ("you"), active voice
- Sentence case for headings
- User-facing docs: outcome-focused, no internal file paths
- Developer docs: include file paths, API shapes, migration names

## Updating docs

When shipping a feature in AdeHQ:

1. Update the relevant PRD or feature page under `prds/` or `features/`
2. Add API changes to `api/` with request/response shapes
3. Add migrations to `database/migrations.mdx`
4. Add a versioned entry in `changelog.mdx` (e.g. V16.8, V17)
5. Update `platform/architecture.mdx` if the pipeline changed
6. Update user-facing guides if the product surface changed

## Local preview

```bash
npm i -g mint
mint dev
```

## Mintlify MCP

Use the Mintlify dashboard MCP in Cursor to edit pages and open PRs on this repo. Credentials: `MINTLIFY_CLIENT_ID` and `MINTLIFY_CLIENT_SECRET` in AdeHQ `.env.local`.
