# delightful-claude-plugin

Claude Code plugin that packages Delightful design-system context as skills, agents, reference docs, theme exports, and an MCP server.

## Source of Truth

Reference docs and theme exports are curated snapshots from [delightful.build](https://delightful.build/). Keep this repo internally consistent and update snapshots intentionally.

## Validate

```sh
npm install --prefix mcp-server
npm start --prefix mcp-server
```

For MCP protocol checks, start the server and verify the advertised tools exist: `lookup_token`, `lookup_component`, `map_color`, `audit_css`, and `get_token_css`.

## Editing Rules

- Keep versions synchronized across `plugin.json`, `marketplace.json`, `mcp-server/package.json`, and the `McpServer` constructor.
- Preserve portable `${CLAUDE_PLUGIN_ROOT}` usage in `.mcp.json`.
- Agent tool scopes are intentional: auditor read-only, builder/composer write-capable.
- Skill frontmatter `allowed-tools` uses YAML array format.

## Screenshots

Screenshots should represent the current Delightful visual language. Refresh them when the public design system pages or token presentation changes substantially.
