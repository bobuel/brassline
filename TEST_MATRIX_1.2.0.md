# Brassline 1.2.0 — release verification

Date: 9 September 2026. Runtime: official Godot 4.7.1 (`a13da4feb`), Windows headless console. This is automated engine verification, **not visual certification or moderated player research**.

## Canonical README regression matrix

Final result: **38 / 38 canonical scripts pass in their intended modes.** Each pass requires its assertion banner and no GDScript exception, parser/compiler error, or application backtrace in that test's final invocation. A printed PASS alone is insufficient. The dead-operative off-tree weapon-drop error found during preparation was fixed, and the affected preparation/integration tests were rerun clean.

Evidence paths below are relative to the repository workspace. `G/<name>` means `work/trust-pass/<name>_uplift.log`. `F/<name>` means `work/trust-pass/<name>_release_final.log`, recorded after the final large-text UI fix. `UI` means `work/ui-lift-20260909/release-ui-hotfix.log`, whose named `UI_EXIT=0 TEST=<script>` separates each passing invocation. The UI log's before/after source hashes match the frozen files. All previous logs are preserved. Headless presentation/layout tests inspect scene structure and geometry; they do not inspect rendered pixels.

| # | Canonical script | Result | Actual scope / evidence |
| --- | --- | --- | --- |
| 1 | combat_smoke | PASS | Four-zone shots, AP, paired mesh limbs and penalties. `G/combat_smoke` |
| 2 | character_asset_smoke | PASS | Six imported rigs, required bones and animation tracks. Not animation-quality certification. `G/character_asset_smoke` |
| 3 | environment_asset_smoke | PASS | 38 loaded CC0 models, palette textures and blocker masking. `G/environment_asset_smoke` |
| 4 | campaign_flow_smoke | PASS | Title/continue, crew rotation, route-first choice, treatment targeting and boarding. `UI` |
| 5 | between_car_recovery_smoke | PASS | Triage, exact body zones, treatment previews/effects, dead-crew handling and checkpoints. `UI` |
| 6 | run_state_smoke | PASS | 360 adversarial state runs, route compliance, inventory, v7/legacy checkpoints. `G/run_state_smoke` |
| 7 | seven_car_integration_smoke | PASS | Draft, opening, route, dead-crew preparation, checkpoint restore and persistent kit. `G/seven_car_integration_smoke` |
| 8 | car_archetype_smoke | PASS | Distinct authored threat profiles and Sleeper event. `G/car_archetype_smoke` |
| 9 | car_presentation_smoke | PASS | Seven single-car scene structures, windows, cover alignment and framing. `G/car_presentation_smoke` |
| 10 | logical_spawn_smoke | PASS | Car-aware roles, unique safe positions and physical cover posts. `G/logical_spawn_smoke` |
| 11 | full_run_soak | PASS | Legacy scene/campaign flow, items and checkpoints; **forces encounter completion**, not autonomous combat evidence. `G/full_run_soak` |
| 12 | full_turn_playthrough | PASS | Real manual Standard policy, seven cars, all three survive; 59 shots, 26 moves, 11 enemy turns, real Overwatch reaction. `G/full_turn_playthrough` |
| 13 | hud_layout_smoke | PASS — legacy manual | Retained manual targeting/cover-preview layout, not the shipping autobattle UI. `UI`, explicit manual mode |
| 14 | car_buff_ui_smoke | PASS | Exact rewards, cumulative buffs, preparation and operative stat detail. `UI` |
| 15 | enemy_tactics_smoke | PASS | Contextual cover, stance/AP and role-aware movement/brace. `G/enemy_tactics_smoke` |
| 16 | enemy_tactics_simulation | PASS | 756 decisions, seven cars, 18 seeds; role divergence 126/126; selected cover 65.9%. `G/enemy_tactics_simulation` |
| 17 | autobattle_vertical_slice_smoke | PASS | Planning, deployed orders, initiative, body doctrine, pace, aftermath and persistence. `G/autobattle_vertical_slice_smoke` |
| 18 | autobattle_dining_smoke | PASS | Officer/Bruiser context, authored offers and actual chandelier leg damage. `G/autobattle_dining_smoke` |
| 19 | autobattle_plan_permutations | PASS | Four rosters, casualties, injuries, role binding and safe offer. `G/autobattle_plan_permutations` |
| 20 | autobattle_consumable_smoke | PASS | Focus Tonic trigger, consumption, intent and telemetry. `G/autobattle_consumable_smoke` |
| 21 | autobattle_grenade_smoke | PASS | Explicit commitment, legal approach, throw, damage and inventory decrement. `G/autobattle_grenade_smoke` |
| 22 | autobattle_deployment_safety | PASS | 162 scenarios / 648 plans; six operatives, one–three survivors, nine cars, three variants; five-tile minimum opposing gap. Requires four offers. `G/autobattle_deployment_safety` |
| 23 | planning_visibility_smoke | PASS | Final post-fix rerun: 108 plan views / nine combat cars / 720p, 800p and 1080p geometry; board, enemy Ledger and details. `F/planning_visibility_smoke` |
| 24 | takeover_refinement_smoke | PASS | Distinct families/targets, committed gear, surrender and objective takeover. `G/takeover_refinement_smoke` |
| 25 | autobattle_full_run | PASS — baseline | Post-final-fix safe Story seed 96001 completes all seven cars at 1x/2x/4x. Additional risky policies include a **real Standard defeat**, detailed below. `F/campaign_safe_story_1x` |
| 26 | signature_arc_smoke | PASS | Three authored hazards, telegraphs, doctrine counters and persistent crew consequences. `G/signature_arc_smoke` |
| 27 | signature_arc_playthrough | PASS | Boarding, Dining and Engine won by automatic initiative; control capture and aftermath persist. `G/signature_arc_playthrough` |
| 28 | full_car_authorship_smoke | PASS | Nine car hazards, controls, guaranteed authored counters and anatomical doctrine breaks. `G/full_car_authorship_smoke` |
| 29 | full_authored_arc_playthrough | PASS | Nine combat archetypes won through real automatic initiative; 26 total rounds, Engine five rounds. Original must-win assertion retained. `G/full_authored_arc_playthrough` |
| 30 | crew_council_smoke | PASS | Three act-break choices, exact tradeoffs, persistence, memories and ending influence. `G/crew_council_smoke` |
| 31 | campaign_epilogue_smoke | PASS | Named outcomes, route, grade and individual epilogues. `G/campaign_epilogue_smoke` |
| 32 | audio_director_smoke | PASS | 25+ loaded CC0 cues, playback pool, ambience, hooks and captions. Not listening evaluation. `G/audio_director_smoke` |
| 33 | failure_recovery_smoke | PASS | Defeat/retry and atomic pre-fight restoration of crew, supplies, telemetry and planning. `G/failure_recovery_smoke` |
| 34 | teen_readiness_plan_smoke | PASS | Four tactical families, repetition caps, eligible gear and deployment/preview contracts. `G/teen_readiness_plan_smoke` |
| 35 | onboarding_controller_smoke | PASS | Start Heist, default trio, four prompts, fallback redraw, controller focus/legends and 130% text. `UI` |
| 36 | presentation_failure_smoke | PASS | Ordered beats, actual failure cause, exposure, decisive injury and fallback protection. `G/presentation_failure_smoke` |
| 37 | profile_progression_smoke | PASS | Independent v2 migration, sidegrades, scars, relationships and deterministic challenge/daily codes. `G/profile_progression_smoke` |
| 38 | heist_share_card_smoke | PASS | 1280x720 scene composition and record fields. Not proof of exported pixels or browser download. `G/heist_share_card_smoke` |

The canonical total counts scripts once, not scenario count or repeated seeds. The baseline row 25 pass must not be restated as “all campaign policies won.”

The preserved earlier `work/ui-lift-20260909/final-ui-matrix.log` retains an initial **incorrect-mode failure** of `hud_layout_smoke` with `--autobattle-test`: that legacy fixture expects manual move/cover previews, intentionally disabled in the shipping autobattler. Its correct manual invocation subsequently passed without changing its assertions, and the final `UI` log repeats that correct-mode pass. The separate modern `autobattle_ui_layout_smoke` passed in autobattle mode; the legacy pass is not used to claim modern UI coverage.

## Final gameplay campaigns and speed determinism

These are real headless automatic-initiative runs with the default Ada/Marlow/Nix trio, strategy 0 and normal run treatments. No forced damage, victories or healing are used by this campaign harness.

| Policy | Seed / selected pace | Outcome | Evidence |
| --- | --- | --- | --- |
| Safe / Story | 96001 / 1x | Post-final-UI-fix seven-car win; all three survive; 76 shots, 27 rounds. Six combat cars plus Sleeper. | `F/campaign_safe_story_1x` |
| Safe / Story | 96001 / 2x | Identical result and final simulation record. | `F/campaign_safe_story_2x` |
| Safe / Story | 96001 / 4x | Identical result and final simulation record. | `F/campaign_safe_story_4x` |
| Varied / Standard / Improvise | 96001 / 2x | **DEFEAT**, Dining round 3; Nix had already fallen in Crew. Blueprint Crossfire retained no protective fallback resistance. | `G/campaign_varied_standard_2x` |
| Risky environmental / Story | 96002 / 4x | Seven-car win; Ada survives at 10/12 torso; Marlow and Nix lost in Crew. 46 shots, 14 limb shots. | `G/campaign_risky_story_4x` |
| Extra paired Safe / Standard | 96001 / 2x | Seven-car win; all three survive; 69 shots, 26 rounds. Same seed/difficulty as the varied loss. | `G/campaign_safe_standard_2x` |

The three post-final-fix safe Story logs contain nonempty, byte-identical **2,870-character JSON payloads** (2,891 characters including the `AUTOBATTLE OUTCOME / ` log prefix), covering the route, crew bodies/memories, relationships, inventory, buffs and all run statistics. Each also exactly matches its preserved pre-layout-fix `G` baseline. The comparison checks a nonzero record length before equality; null equality is not accepted as determinism evidence. This comparison was repeated at 10:30 EDT after the final UI production freeze.

The varied Standard harness exits 1 because its victory assertion is not satisfied. This remains an observed loss, not a secretly converted test pass. Its causal record identifies the Dining Bruiser's five-point torso hit making Marlow critical, the final Railhand hit on Ada, no protection under Improvise, and the committed grenade still waiting. A single paired seed establishes decision consequence, not broad balance or a population win rate.

## Additional targeted regressions

These are **outside** the canonical 38 and are not added to that denominator. All pass with evidence at `G/<script>`:

- `gameplay_uplift_smoke`: truthful Voss command risk, control advance held until actual disarm/neutralization, arms-to-legs targeting, conditional capture and stable safe retreat.
- `audit_gameplay_regressions`: pre-attack protection, independent inspection pause, shared bounded environmental footprint, presentation RNG isolation, item retry, accurate casualty causes and sidegrade eligibility.
- `autobattle_fallback_smoke`: Finish Target, Protect Wounded, Save Crew and role-specific Improvise.
- `convergence_pace_smoke`: semantic 1/2/4 mapping to 0.5/1/2 engine scale, pause/resume, inspect slowdown and menu reset.
- `convergence_copy_budget_smoke`: concise car, plan, council, fallback, bark and epilogue budgets.

Also verified in final `UI`, all PASS/exit 0: `ui_lift_smoke` (in-run settings, character persistence, item commitment, Head effects, doctrine discovery and 130% layout); `ui_trust_smoke` (stable actor/tab/focus/rotation, enemy inspection, independent modal pause, settings and challenge import); `autobattle_ui_layout_smoke` (docked planning details, full-screen Ledger, 80% combat carriage area and aftermath fit); and new `ui_overflow_smoke` (active signal updates, early/late routes, preparation, long aftermath/reward detail and end-card at 720p/130%). The layout fixture now allows three actual layout-settle frames before measuring its already-visible aftermath controls; its bounds and terminal assertions are unchanged. None of these headless runs is rendered visual proof. The UI owner separately ran the overflow fixture with active OpenGL and captures (`work/ui-lift-20260909/overflow-gl.stdout.log`). Weapon/share-pipeline supplementary tests and live Web checks are tracked by their owners.

## Reproduction and scope

Run from the workspace with APPDATA redirected to `work/trust-pass/userdata-gameplay` so tests do not touch the player's normal profile. Command shape:

```powershell
$env:APPDATA = 'C:/Users/bobue/Documents/Codex/2026-08-17/weha/work/trust-pass/userdata-gameplay'
& 'C:/Users/bobue/Documents/Codex/2026-08-17/weha/work/trust-pass/runtime/Godot_v4.7.1-stable_win64_console.exe' --headless --fixed-fps 60 --path 'C:/Users/bobue/Documents/Codex/2026-08-17/weha/outputs/BrasslineGodot' --log-file '<absolute log path>' --script 'res://tests/<script>.gd' -- --autobattle-test
```

The shipping autobattle fixtures use `--autobattle-test`. The legacy manual/scene fixtures (combat, assets, run-state, seven-car integration, archetypes/presentation/spawn, manual full-run/full-turn, enemy tactics, council/epilogue, audio/profile/share-card) omit it. The UI matrix's passing modern fixtures use `--autobattle-test`; `hud_layout_smoke` omits it. Campaign arguments are `--auto-seed=96001 --auto-strategy=0 --auto-roster=0 --auto-difficulty=story --auto-speed=1`; vary the documented seed, difficulty and pace, adding `--auto-risky=true` and, for the environmental policy, `--auto-hazard=true`.

Existing restricted-runtime certificate-store messages and headless RID/ObjectDB/resource cleanup diagnostics remain in some exit logs. They are not assertion or gameplay exceptions and are not concealed as “no warnings.” They still merit cleanup; this matrix does not certify a leak-free application.

The prior Engine must-win failure was corrected through connected conditional orders, not health/damage buffs. The prior manual Standard failure used a weak test-bot policy (forfeiting crew AP after Overwatch, bracing instead of shooting, and closing pointlessly for grenades). Its policy was improved without weakening its victory/action/checkpoint assertions; old loss logs were retained. See `work/trust-pass/GAMEPLAY_UPLIFT_20260909.md` for causes and rejected experiments.

Final simulation source SHA256:

- `autobattle_director.gd`: `4843EADD9ED728239BEEC2EFB941F3DE94575106E8ACB792F0E74A1ADCD73F7F`
- `plan_catalog.gd`: `9FB34050B94E881D52A4C202CF9B00A11B6867BA47C068E4CD63202F2C00FAEE`
- `turn_controller.gd`: `B16D16EF480B3C7FC644987EF0B6EB6F22172209DFAF93C54595B74359AD9C10`

Final large-text UI source SHA256 (matching the UI regression log's start/end and post-campaign files):

- `campaign_ui.gd`: `282172FFF9170BD3394327517A24660EE58E8BE848AE72A224EFBFE36EA44A46`
- `autobattle_ui.gd`: `10BA1C00B7C517B26863D514FC8A604F57FA57D7FBC25BAB1A6C719D382CDE09`

Native rendered visual inspection, Windows/Web export, live GitHub Pages launch, browser console checks, and five moderated teenage first-session tests are **not established by these automated script results**. Do not claim those acceptance items from this document alone.

