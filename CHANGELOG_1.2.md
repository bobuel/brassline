# Brassline 1.2.0 — Character & Clarity Lift

September 9, 2026. Free, local-first, single-player train-heist autobattler.

## What changed

- Rebuilt the six weapon silhouettes with shaped stocks, open barrels, brass details and credible scale. Added supporting-arm poses to the existing animated rigs.
- Replaced generic cover blocks with readable luggage, dining tables, lockers and fitted industrial cargo; quieted busy carriage materials. Furniture occupancy and the tactical grid remain aligned.
- Kept character-focused selection and the full-screen rotating Crew Ledger. Inventory cards now show the correct complete item, actual quantity, plan commitment, safe trigger and whether it was used this car. Injuries explain their four-zone effects.
- Added mid-run settings from the Ledger and compact pace control. Returning restores the selected character, tab, focus and previous pause state. Difficulty cannot change during a run.
- Corrected browser-found large-text overflows in late-route buffs, active combat text, wounded preparation, long aftermath rewards and expanded run details. Route cards have explicit Board/Review actions; combat status is a short state label; reward breakdowns are optional while Continue stays visible.
- Fixed Ledger enemy identity, inspection pause, grenade retries and inventory freshness, bounded area hazards, protection/preview discrepancies, critical-injury guidance and surrendered-unit support actions from the trust audit.
- Made Engine's pressure plan a conditional sequence: disable Voss's arms, then legs, and advance to the controls after disarming. Venting does not silently remove his head-based command doctrine. Preview and failure analysis say so.
- Corrected rifle stand-off positioning and repeated retreats from already safe positions. No health, damage or random probabilities were inflated to force victories.
- Added ready-before-click heist-card export with crew portraits, actual current-run wounds/casualties, grade and challenge code. Historical profile scars are not mislabeled as current injuries.

## Preserved

Seven-car route rules, anatomical targeting, ammunition, initiative, deterministic outcomes, persistent injuries, profile/checkpoint formats and CC0 attribution. Visible 1x / 2x / 4x still means effective 0.5 / 1 / 2 engine speed. Shift/LT inspection slowdown remains available. No accounts, servers, purchases or new content systems.

## Build from source

Use Godot 4.7.1 with matching export templates. Open the project once to import assets. Web export uses GL Compatibility and disables threads; it needs an HTTP(S) server, not a file URL.

```text
godot --headless --editor --path BrasslineGodot --quit
godot --headless --path BrasslineGodot --export-release Web ../Web/brassline_1_2_0.html
godot --headless --path BrasslineGodot --export-release "Windows Desktop" ../Windows/Brassline.exe
```

The source archive includes assets, import settings, scenes, scripts, tests and credits. It excludes editor caches, user saves, screenshots, downloaded runtimes and local credentials. See the published release verification for test results; automated tests are not a substitute for moderated player testing or physical-controller certification.

