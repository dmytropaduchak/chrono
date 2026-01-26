# Chrono

A minimal pixel clock inspired by the GitHub contributions heatmap. Time is rendered as pixel text inside a fixed square grid, with a dark GitHub-style backdrop and configurable accent colors.

![screenshot](https://github.com/dmytropaduchak/chrono/main/img/screenshot.png)

## ⬇️ Download

![macOS](https://github.com/dmytropaduchak/chrono/dmg/Chrono.dmg)

## Features
- Pixel-font digits rendered from 5x7 glyph maps (no text rendering).
- GitHub-style grid cells with subtle noise pixels.
- Toggle 12h / 24h time format and optional AM/PM indicator.
- Date line rendered in a smaller pixel grid.
- Theme cycling with multiple GitHub-inspired accent colors.
- GitHub integration: shows your open PRs (requires a PAT).

## Controls
- `C` Toggle theme color
- `H` Toggle 12h / 24h

## Build and Run
```bash
cargo run
```

## GitHub Token
To show your open PRs, set a classic GitHub PAT with access to your repos.

```bash
export GITHUB_TOKEN=your_token_here
```

Or create `~/.config/chrono/token` with the token.

## Structure
- `src/main.rs` contains:
  - Pixel font definition
  - Grid renderer
  - Clock formatting and layout logic
  - Theme configuration

## Notes
- The grid and glyphs are easy to extend for new modes (e.g., inverted grid or GitHub API overlays).
- The display redraws once per frame with a low-cost loop suitable for 1 Hz updates.
