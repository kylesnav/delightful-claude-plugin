<p align="center">
  <picture>
    <source media="(prefers-color-scheme: dark)" srcset="screenshots/Delightful-Dark.png" />
    <source media="(prefers-color-scheme: light)" srcset="screenshots/Delightful-Light.png" />
    <img src="screenshots/Delightful-Light.png" width="600" alt="Delightful Design System" />
  </picture>
</p>

<h1 align="center">Delightful Design System — Claude Code Plugin</h1>

<p align="center">
  The Delightful design system as AI-accessible context. Build, refactor, audit, and present UI with neo-brutalist tokens, OKLCH colors, and solid shadows.
</p>

---

## Install

```bash
claude plugin install kylesnav/delightful-claude-plugin
```

## What You Get

### MCP Tools

| Tool | What it does |
|------|-------------|
| `lookup_token` | Look up tokens by name or category — returns value, tier, and usage guidance |
| `lookup_component` | Get the full CSS + HTML pattern for any of 20+ components |
| `map_color` | Find the closest Delightful token for any hex/rgb/oklch color |
| `audit_css` | Check a CSS snippet for design system violations with fix suggestions |
| `get_token_css` | Return the complete token stylesheet for copy/paste |

### Agents

| Agent | When to use |
|-------|------------|
| `delightful-auditor` | Read-only compliance checker — scans for hardcoded values, missing states, accessibility gaps |
| `delightful-builder` | Construct pages and components using strict design system patterns |
| `delightful-composer` | Assemble components into complete page layouts with responsive behavior and dark mode |

### Skills

| Command | What it does |
|---------|-------------|
| `/build-with-delightful` | Build new UI from scratch — scaffolds tokens, builds components, audits for compliance |
| `/refactor-with-delightful` | Migrate existing UI to the design system — audits first, plans migration, replaces systematically |
| `/audit-with-delightful` | Run a compliance scan — hardcoded values, missing interaction states, accessibility gaps, dark mode breakage |
| `/present-with-delightful` | Generate slide deck presentations with keyboard nav, sidebar TOC, search, and theme toggle |

### Reference Docs

Browsable via `delightful://` resources:

| Doc | Content |
|-----|---------|
| `tokens.md` | All 3 tiers of token values |
| `components.md` | 20+ component patterns with CSS/HTML |
| `interactions.md` | POUNCE/SINK press patterns, motion, animations |
| `composition.md` | Page layouts, responsive, utilities, checklist |
| `philosophy.md` | Design rationale and principles |
| `accessibility.md` | WCAG contract, contrast, focus model |
| `animations.md` | 56 CSS @keyframes across 10 categories |
| `color-system.md` | OKLCH color architecture and dark mode shifts |
| `motion-js.md` | Spring physics, FLIP, particles, gestures |
| `porting-guide.md` | How to create new platform themes |
| `governance.md` | How to safely extend the token system |

### Theme Exports

Drop-in theme files for any project:

**CSS Custom Properties** — `themes/css/delightful-tokens.css`
```css
@import './themes/css/delightful-tokens.css';
```

**Tailwind Preset** — `themes/tailwind/delightful-preset.js`
```js
// tailwind.config.js
import delightfulPreset from './themes/tailwind/delightful-preset.js'
export default { presets: [delightfulPreset] }
```

**Figma / Style Dictionary** — `themes/figma/tokens.json`
Design Tokens Community Group format. Import into Figma with Tokens Studio or process with Style Dictionary.

## Usage Examples

### Build a component

```
/build-with-delightful
"Build a settings page with a form, toggle switches, and a save button"
```

Claude reads the reference docs, scaffolds the token foundation, builds the page with proper OKLCH colors, solid shadows, POUNCE/SINK interactions, and dark mode — then audits for compliance.

### Migrate existing code

```
/refactor-with-delightful
"Refactor this React app to use the Delightful design system"
```

Claude audits your current code, presents a migration plan, executes each phase, and re-audits until there are zero violations.

### Quick token lookup

```
"What spacing token is closest to 24px?"
```

The MCP server responds instantly: `--space-6: 24px` — no skill invocation needed.

## Claude Desktop

The MCP server also works standalone in Claude Desktop. Add to your `claude_desktop_config.json`:

```json
{
  "mcpServers": {
    "delightful": {
      "command": "node",
      "args": ["/path/to/delightful-claude-plugin/mcp-server/index.js"]
    }
  }
}
```

Then install dependencies: `cd /path/to/delightful-claude-plugin/mcp-server && npm install`

## Part of Delightful

This plugin is the AI interface to the [Delightful Design System](https://github.com/kylesnav/delightful-design-system). The canonical reference lives at [kylesnav.github.io/delightful-design-system](https://kylesnav.github.io/delightful-design-system/delightful-design-system.html).

Related packages:
- [delightful-design-system](https://github.com/kylesnav/delightful-design-system) — Canonical reference, HTML spec, and documentation
- [delightful-css](https://github.com/kylesnav/delightful-css) — Standalone CSS tokens package
- [delightful-tailwind](https://github.com/kylesnav/delightful-tailwind) — Tailwind CSS preset
- [delightful-figma](https://github.com/kylesnav/delightful-figma) — Figma tokens (DTCG format)

## License

[MIT](LICENSE)
