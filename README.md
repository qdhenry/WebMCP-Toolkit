# WebMCP Toolkit

A Claude Code plugin that provides expert-level guidance for implementing [WebMCP](https://nicolo-ribaudo.github.io/anthropic-webmcp/) in web projects — browser-native structured tools that let AI agents interact with websites through typed APIs instead of screen-scraping.

## What is WebMCP?

WebMCP is a browser-native standard (Chrome 146+) that exposes structured tools for AI agents on websites. It provides two APIs:

- **Imperative API** — `window.navigator.modelContext` — register tools via JavaScript with full programmatic control
- **Declarative API** — HTML `toolname`/`tooldescription` attributes on `<form>` elements for zero-JS tool exposure

## What's Included

### Slash Commands

| Command | Description |
|---------|-------------|
| `/webmcp` | Main entry point — routes to setup, add-tool, debug, audit, or test workflows |
| `/webmcp-setup` | Set up WebMCP in a project from scratch |
| `/webmcp-add-tool` | Add a new imperative or declarative tool |
| `/webmcp-debug` | Diagnose and fix WebMCP issues |
| `/webmcp-audit` | Audit an existing implementation against best practices |

### Skill: `webmcp`

A router-pattern skill with full domain expertise:

**Workflows** — Step-by-step procedures for every WebMCP task:
- `setup-webmcp` — Initial integration (prerequisites, strategy selection, tool registration)
- `add-imperative-tool` — Register tools via the JavaScript API
- `add-declarative-tool` — Annotate HTML forms as WebMCP tools
- `debug-webmcp` — Systematic diagnosis (8-step process)
- `audit-webmcp` — Best practices review with severity-categorized reports
- `test-webmcp` — Full testing with the Model Context Tool Inspector extension

**References** — Deep domain knowledge:
- `imperative-api` — Full JS API reference (`registerTool`, `unregisterTool`, `provideContext`, `clearContext`)
- `declarative-api` — HTML form attributes, schema auto-generation, `respondWith` pattern
- `tool-design` — Naming conventions, description patterns, schema design, reliability strategies
- `events-and-css` — `toolactivated`/`toolcancel` events, `:tool-form-active`/`:tool-submit-active` pseudo-classes
- `testing` — Inspector extension usage, console testing, verification checklists
- `anti-patterns` — 10 common mistakes with bad/good code examples

**Templates** — Ready-to-use scaffolding:
- `imperative-tool` — Single tool, multi-tool, and SPA lifecycle patterns
- `declarative-form` — Basic forms, auto-submit forms, event listeners, custom CSS

## Installation

Add the plugin to your Claude Code settings (`.claude/settings.json`):

```json
{
  "plugins": [
    "qdhenry/WebMCP-Toolkit"
  ]
}
```

Then use any of the slash commands (e.g., `/webmcp-setup`) or invoke the skill directly.

## Prerequisites

- Chrome 146.0.7672.0 or later
- `chrome://flags/#enable-webmcp-testing` flag enabled
- [Model Context Tool Inspector](https://nicolo-ribaudo.github.io/anthropic-webmcp/) Chrome extension (for testing)

## Plugin Structure

```
.claude-plugin/
  plugin.json          # Plugin manifest
skills/
  webmcp/
    SKILL.md           # Router + essential principles
    workflows/         # 6 step-by-step procedures
    references/        # 6 domain knowledge files
    templates/         # 2 scaffolding templates
commands/
  webmcp.md            # Main entry point
  webmcp-setup.md      # Quick start
  webmcp-add-tool.md   # Add a tool
  webmcp-audit.md      # Audit implementation
  webmcp-debug.md      # Debug issues
```

## License

MIT
