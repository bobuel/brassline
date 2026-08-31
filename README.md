# Brassline: Train Heist — Web Build

Static Godot 4.7.1 Web export for GitHub Pages. Open `index.html` through an HTTP server; browsers do not permit loading the game directly from the filesystem.

- Build: UI Clarity 1.1.2
- Combat pace: visible 1x / 2x / 4x maps to 0.5 / 1.0 / 2.0 simulation scale
- Interface: compact planning and combat modes plus the full-screen Crew Ledger
- Renderer: GL Compatibility
- Threading: disabled for standard GitHub Pages hosting
- Main bundle: cache-safe `ui_clarity.pck` + `ui_clarity.wasm`

The canonical source project is maintained separately in `outputs/BrasslineGodot`.
