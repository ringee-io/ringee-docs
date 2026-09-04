# Ringee documentation

This repository contains the public Ringee documentation built with [Mintlify](https://mintlify.com).

The technical source of truth is the [`ringee-io/ringee-app`](https://github.com/ringee-io/ringee-app) repository. Verify endpoints, tool schemas and CLI flags there before changing a reference page.

## Sections

- self-hosting and configuration;
- Custom Integration Public API;
- MCP and AI apps;
- `ringee` CLI;
- AI Voice Agents;
- Dialer SDK.

## Development

Install the [Mintlify CLI](https://www.npmjs.com/package/mint):

```bash
npm i -g mint
```

From this directory, start the local preview:

```bash
mint dev
```

View it at `http://localhost:3000` and check links before opening a pull request:

```bash
mint broken-links
```

## Publishing changes

Changes pushed to the configured default branch are deployed through the Mintlify GitHub app.

See `AGENTS.md` for terminology, style and canonical implementation paths.
