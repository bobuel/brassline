# Brassline: Train Heist

[Play Brassline](https://bobuel.github.io/brassline/) — free, single-player, seven-car steampunk heist autobattler.

## 1.2.0 — Character & Clarity Lift

Choose a crew, read the carriage, pick a plan and a fallback, then watch the crew carry it out. Disable weapons with arm shots, stop advances with leg shots, exploit carriage machinery and keep the survivors fit for the next car.

This release rebuilds the weapons and supporting-hand poses; gives luggage, tables and lockers recognizable shapes; improves character inspection and item status; adds safely paused mid-run settings; and corrects Engine-plan sequencing, hazard/protection previews, enemy inspection and retreat behavior.

- **Start Heist** uses the default trio; inspect and rotate characters before boarding.
- Click crew portraits or press **I / controller Y** for the Crew Ledger. Crew, Gear, Injuries and Train tabs keep management separate from combat.
- **1 / 2 / 4** chooses pace. The visible 1x setting runs at half engine speed; 2x and 4x scale proportionally. **Shift / LT** slows inspection further.
- A plan commits available grenades or tonics automatically. Gear shows the assigned operative, safe trigger and used status; Medkits and Braces are for between-car treatment.
- **Settings** remains available mid-run without changing difficulty or losing selection/pause state. Text supports 100%, 115% and 130%; Reduced Motion and cinematic focus are optional.
- Finish a run to save an illustrated heist card or copy its challenge code. Runs and profiles stay in this browser/device; no accounts or servers.

## Source and builds

[Download the complete 1.2.0 Godot source](brassline-1.2.0-source.zip). It includes the six CC0 rigs, environment/audio assets, import settings, scenes, scripts, tests and attribution. Open `BrasslineGodot/project.godot` in **Godot 4.7.1**, allow import, and press F5. `CHANGELOG_1.2.md` inside the archive documents export commands and changes.

The Web build uses GL Compatibility / WebGL 2 and **no threads**. Serve it over HTTP(S); opening the HTML from disk does not work. Cache-versioned `brassline_1_2_0.*` files distinguish this release from older bundles. Windows is also exported and verified locally.

## Verification and limits

See [release checks](VERIFICATION_1.2.0.md) and [the regression matrix](TEST_MATRIX_1.2.0.md). Automated checks are not a claim that every risky policy wins, that every seed is balanced, or that moderated teenager usability/physical-controller certification has been completed.

No paid assets, monetization, multiplayer or account system. Asset sources and licenses are retained in [asset credits](ASSET_CREDITS.md) and the source archive.

