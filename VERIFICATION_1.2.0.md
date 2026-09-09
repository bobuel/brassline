# Brassline 1.2.0 release verification

September 9, 2026. Godot 4.7.1; Windows GL Compatibility and non-threaded WebGL 2 exports.

## What was verified

- The retained 38-test regression matrix passes in each fixture's intended mode. See [the matrix](TEST_MATRIX_1.2.0.md), which distinguishes automated results from visual certification.
- Three final seven-car Story campaigns (seed 96001, default trio, safe policy) at 1x, 2x and 4x all win with all three crew surviving. Their complete 2,870-character outcome records are identical, and match the pre-layout-fix simulation baseline: 76 shots and 27 rounds.
- Risky Story also wins with casualties. A varied Standard run legitimately loses in Dining; safe Standard on the same seed wins. These are recorded outcomes, not a guarantee that every policy or seed wins.
- Ten post-fix UI checks pass. Added adverse-state coverage exercises accumulated route buffs, live combat text, long reward summaries and expanded completion details at 130% text in 1280x720, 1280x800 and 1920x1080 layouts. Planning visibility passes 108 views.
- Rendered graphics checks cover the six weapon/character setups, idle/aim/fire frames and carriage props. Final UI renders include 24 adverse-state captures across the three resolutions. Character support poses, weapon mounting and recognizable luggage/table/locker shapes were inspected.
- Actual exported-browser play reached Engine after clearing Boarding, Sleeper, Armory, Crew, Dining and Bar. Ordinary UI interactions verified character rotation, Ledger tabs, treatment counts/HP, protective fallbacks, environmental plans, mid-fight Settings/manual-pause restoration and 130% text. Browser errors/warnings were empty through that checkpoint.
- That browser playthrough found late-run overflow and overlapping combat text missed by the initial fixtures. Those defects were fixed, regression-tested and re-rendered before export. The final browser build successfully resumed the saved pre-Engine checkpoint, displayed the corrected route/preparation/planning screens and ran the pressure-control encounter through round two. The test tab was subsequently closed; its final outcome and actual browser PNG download were not observed. They are not claimed as completed checks.
- Share-card automated/native-render checks verify portraits, current wounds, fallen crew, challenge identity, PNG generation and native saving. The browser download path now uses a pre-rendered image synchronously from the click handler; an end-to-end browser download remains a follow-up check.
- Final Windows embedded-pack executable and non-threaded Web exports succeed. The exported Windows build launches with active OpenGL. A source-archive round-trip verified clean import and launch; every one of the final archive's 365 entries was independently compared with current source and matched exactly.

## Artifact identity

- Web pack: `brassline_1_2_0.pck`, 9,404,272 bytes. SHA256: `627f197050e6ba16abb915aee510d6873fca499d4f6b0a1769644bd675252ec5`.
- Complete source: `brassline-1.2.0-source.zip`, 11,061,157 bytes. SHA256: `bec8d604a04389ea1b23f74dba09aac293a8b5eaf158386d93e2415b45630df6`.
- Versioned HTML/JS/WASM/pack names prevent the new entry page from silently using an older pack. Older repository bundles are retained for history.

## Limits

Native runs still emit restricted-environment certificate-store warnings and some scene-test shutdown resource diagnostics. This is not a leak-free certification. No physical-controller certification, five moderated teen sessions, exhaustive seed balance or commercial-readiness claim is made. This is a substantial playable prototype lift, not a finished commercial release.

Live publication is verified separately after the GitHub Pages deployment; this document records pre-publication evidence without pretending a deployment has already passed.

