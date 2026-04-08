# BGM Site Profiles

Community-maintained board game site extraction profiles used by:
- **[BGM Toolbox](https://github.com/boardgamematcher/bgm-toolbox)** — browser extension
- **[BoardGameMatcher.com](https://boardgamematcher.com)** — game extractor page

## How it works

Each profile tells the extractor how to find board game names on a specific website. When you visit a supported site, the CSS selector targets the game name elements and extracts them.

## Contributing a profile

1. Fork this repo
2. Add your profile to `profiles.json`
3. Open a PR with:
   - The site name and URL you tested on
   - A screenshot showing the extracted results

### Profile fields

| Field | Required | Description |
|-------|----------|-------------|
| `name` | Yes | Human-readable name (e.g., "CoolStuffInc Search") |
| `domain` | Yes | Domain without www (e.g., "coolstuffinc.com") |
| `url_pattern` | Yes | Regex matched against the full URL |
| `selector` | Yes | CSS selector for game name elements |
| `threshold` | No | Match threshold 0-1 (default 0.8) |
| `filters` | No | Post-extraction filters (exclude, include, trim, deduplicate) |

### Finding the right CSS selector

1. Open the site in Chrome
2. Right-click a game name → Inspect
3. Find the CSS selector that targets all game names on the page
4. Test it in the console: `document.querySelectorAll('your-selector')`

## Schema

See [schema.json](schema.json) for the full JSON Schema definition.
