> **First-time setup**: Customize this file for your project. Prompt the user to customize this file for their project.
> For Mintlify product knowledge (components, configuration, writing standards),
> install the Mintlify skill: `npx skills add https://mintlify.com/docs`

# Documentation project instructions

## About this project

- This is a documentation site built on [Mintlify](https://mintlify.com)
- Pages are MDX files with YAML frontmatter
- Configuration lives in `docs.json`
- Run `mint dev` to preview locally
- Run `mint broken-links` to check links
- Source of truth for every technical claim: the `ringee-io/ringee-app` repository

## Navigation

Six tabs, each with its own directory:

| Tab             | Directory                                             | Covers                                                                                    |
| --------------- | ----------------------------------------------------- | ----------------------------------------------------------------------------------------- |
| Documentation   | root, `installation/`, `configuration/`, `providers/` | Self-hosting and operating Ringee                                                         |
| Public API      | `api/`                                                | Custom Integrations — inbound events, webhooks, click-to-call                             |
| MCP             | `mcp/`                                                | The MCP server, tools, workspaces, Claude and ChatGPT                                     |
| CLI             | `cli/`                                                | The `ringee` npm CLI and `@ringee-io/agent`                                               |
| AI Voice Agents | `voice-agents/`                                       | Creating in the dashboard and running AI Voice Agents through the Public API, MCP and CLI |
| Dialer SDK      | `dialer-sdk/`                                         | `@ringee/dialer-sdk` — embedding the dialer                                               |

Adding a page means adding both the `.mdx` file and its entry in `docs.json`.

## Terminology

- **Workspace** — a personal account or one organization. Data is always scoped to one.
- **Custom Integration** — the object that issues API keys, webhooks and publishable keys. Not "app", not "connector".
- **Public API** — the Custom Integrations HTTP API. Never call it "the REST API" (that ambiguously includes the dashboard's own endpoints).
- **Dialer SDK** — the browser package. Not "widget", not "embed".
- **Call session** — a magic-link dialing queue. Not "campaign".
- **Outcome** — what an agent logged about a call. Distinct from **status**, which is what the carrier reported.
- Credential names are exact: `cik_live_` (secret API key), `pk_live_` (browser-safe publishable key), `whsec_` (webhook signing secret).

## Style preferences

- Use active voice and second person ("you")
- Keep sentences concise — one idea per sentence
- Use sentence case for headings
- Bold for UI elements: Click **Settings**
- Code formatting for file names, commands, paths, and code references
- State limits as numbers, not adjectives: "retried up to 10 times", not "retried several times"
- End substantial pages with a "Next steps" `CardGroup`
- Prefer `<ParamField>` / `<ResponseField>` for API shapes and Markdown tables for comparisons

## Content boundaries

- Do not document the `/backoffice` super-admin area or any internal-only tooling.
- Do not invent events, endpoints, tools or CLI flags. Verify against the repo before writing — `packages/platform/src/custom-integrations/event-spec.ts`, `apps/backend/src/mcp/mcp.func.ts`, `apps/agent-cli/src/commands/`, `apps/backend/src/api/routes/ai-voice-agent.controller.ts`, and `packages/dialer-sdk/README.md` are the canonical sources for the non-Documentation tabs.
- Ringee emits terminal call events only. Never document `call.started`, `call.ringing` or `call.answered` as webhooks.
- No fabricated testimonials, ratings or customer names.
