# Delightful Design System — Claude Code Plugin

A neo-brutalist design system with oklch colors, 3-tier tokens (7 color families), 50+ components, @layer cascade architecture, a CSS motion system, and a JS animation system. Installable as a Claude Code plugin with two skills for building and refactoring UI.

## Installation

### From Marketplace (recommended)

Add the marketplace, then install the plugin:

```shell
/plugin marketplace add kylesnav/delightful-claude-plugin
/plugin install delightful-design-system@delightful-claude-plugin
```

### From Local Clone

Clone the repo and load it directly:

```shell
git clone https://github.com/kylesnav/delightful-claude-plugin.git
claude --plugin-dir ./delightful-claude-plugin
```

## What You Get

### Skills

| Skill | Description |
|-------|-------------|
| `/delightful-design-system:build-with-delightful` | Build a new project from the ground up using the design system |
| `/delightful-design-system:refactor-with-delightful` | Refactor an existing project's UI to use design system tokens |

### Agents

| Agent | Description |
|-------|-------------|
| `delightful-auditor` | Read-only compliance checker — scans for hardcoded colors, missing states, blurred shadows |
| `delightful-builder` | Full-capability UI builder — constructs components/pages following all design system rules |

### Exportable Themes

| Format | File | Usage |
|--------|------|-------|
| CSS Custom Properties | `themes/css/delightful-tokens.css` | Drop into any project |
| Tailwind v3 Preset | `themes/tailwind/delightful-preset.js` | Use as a Tailwind preset |
| Figma / Style Dictionary | `themes/figma/tokens.json` | Import via Tokens Studio or Style Dictionary |

## Design Principles

- **Warm clarity** — Cream backgrounds, near-black text, generous whitespace
- **Surgical color** — Pink for actions, red for danger, gold for highlights, cyan for coolness, green for success, purple for creative
- **Joyful restraint** — Playful but controlled. Spring motion under 240ms.
- **Neo-brutalist** — 2px borders, solid shadows (zero blur), bold typography
- **Systematic** — Every value comes from a token. No magic numbers.

## Token Architecture

```
Tier 1 — Primitives     Raw oklch scales (neutral, pink, red, gold, cyan, green, purple)
Tier 2 — Semantic        Light/dark mode tokens (bg, text, accent, border, shadow)
Tier 3 — Component       Typography, spacing, radius, motion, button, toggle
```

## File Structure

```
delightful-claude-plugin/
├── .claude-plugin/
│   ├── plugin.json              # Plugin manifest
│   └── marketplace.json         # Marketplace catalog
├── skills/
│   ├── build-with-delightful/
│   │   └── SKILL.md             # /build-with-delightful skill
│   └── refactor-with-delightful/
│       └── SKILL.md             # /refactor-with-delightful skill
├── agents/
│   ├── delightful-auditor.md    # Compliance checker agent
│   └── delightful-builder.md    # UI builder agent
├── reference/
│   └── design-system.md         # Full token + component reference
├── themes/
│   ├── css/
│   │   └── delightful-tokens.css    # Standalone CSS tokens
│   ├── tailwind/
│   │   └── delightful-preset.js     # Tailwind v3 preset
│   └── figma/
│       └── tokens.json              # Figma/Style Dictionary tokens
├── LICENSE
└── README.md
```

## Contributing

This is the distribution copy of the plugin. Development happens in the [delightful-design-system](https://github.com/kylesnav/delightful-design-system) monorepo under `claude-plugin/`. To contribute, open issues or PRs there.

## License

MIT
