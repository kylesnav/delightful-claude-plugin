# delightful-claude-plugin

Claude Code plugin — Delightful design system as AI-accessible context.

## Source of Truth

Token values and component patterns come from [delightful-design-system](https://github.com/kylesnav/delightful-design-system). Reference docs in `reference/` are curated snapshots, not auto-generated.

## Setup

```sh
npm install --prefix mcp-server
```

## MCP Server

```sh
npm start --prefix mcp-server
```

5 tools (`lookup_token`, `lookup_component`, `map_color`, `audit_css`, `get_token_css`) and 14 resources (11 reference docs + 3 theme exports) via `delightful://` URIs.

Server code: `mcp-server/index.js` (~530 lines). Uses `@modelcontextprotocol/sdk` + `zod`. OKLCH color math is implemented from scratch — no extra dependencies.

## Key Files

- `plugin.json` — Plugin manifest (name, version, repository)
- `.mcp.json` — MCP server configuration (uses `${CLAUDE_PLUGIN_ROOT}` for portability)
- `mcp-server/index.js` — Tool and resource implementations
- `agents/` — 3 agents: auditor (read-only), builder, composer
- `skills/` — 4 skills: build, refactor, audit, present (all with delightful)
- `reference/` — Curated design system docs (tokens, components, interactions, composition)
- `themes/` — Exported tokens in CSS, Tailwind preset, and Figma JSON formats

## Conventions

- Agent tools are scoped: auditor is read-only (Read/Grep/Glob), builder/composer have write access.
- Skill `allowed-tools` uses YAML array format: `["Bash", "WebFetch"]`.
- All version numbers must stay in sync: plugin.json, marketplace.json, mcp-server/package.json, McpServer constructor.
- Theme exports should match the canonical palette. Known issue: Figma tokens.json may have chroma drift on gold.100.
