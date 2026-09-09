# Asset credits and provenance

## Rigged 3D characters

The six glTF character files in `assets/characters/quaternius/` come from **Ultimate Modular Men Pack** by Quaternius.

- Source: <https://quaternius.com/packs/ultimatemodularcharacters.html>
- Original author: Quaternius
- Original license: CC0 1.0 Universal / Public Domain Dedication
- Included license copy: `assets/characters/quaternius/LICENSE-QUATERNIUS.txt`
- Project-side use: selected whole-character glTF files are loaded directly by Godot; project-authored rifle, breach gun, carbine, pistol, hand-cannon, revolver, targeting-reticle, team-ring, animation, and gameplay components are added at runtime.

Attribution is not required by CC0, but the source is recorded here because keeping asset provenance visible is good practice.

## Modular train and industrial environment

### Crew portrait renders (Trust Pass, September 2026)

The six PNG thumbnails in `assets/ui/portraits/` are engine-rendered portraits of the existing Quaternius CC0 character models, with project-authored lighting and framing. They introduce no new third-party asset license. `tests/render_crew_portraits.gd` reproduces these renders.

The 38 selected GLB models and three shared palette textures in `assets/environment/kenney/` come from three free Kenney packs. Every pack is released under CC0 1.0 Universal.

- **Train Kit** by Kenney: locomotive, coal tender, three carriage underframes, connectors, wheels, and detailed track tiles. Source: <https://kenney.nl/assets/train-kit>. Included license: `assets/environment/kenney/KENNEY-TRAIN-LICENSE.txt`.
- **Factory Kit** by Kenney: machinery, doors, pipes, cogs, screens, controls, crates, pistons, and warning dressing. Source: <https://kenney.nl/assets/factory-kit>. Included license: `assets/environment/kenney/KENNEY-FACTORY-LICENSE.txt`.
- **City Kit (Industrial)** by Kenney: tanks and chimney/flue dressing. Source: <https://www.kenney.nl/assets/city-kit-industrial>. Included license: `assets/environment/kenney/KENNEY-INDUSTRIAL-LICENSE.txt`.

The original model files and palette textures are loaded directly by Godot. Project-authored placement and presentation code widens the rolling-stock underframes into open tactical carriages and preserves the existing invisible blocker grid.

## Sound effects

The 27 OGG files in `assets/audio/kenney/` are selected from four free Kenney audio packs. All four packs are released under CC0 1.0 Universal.

- **Impact Sounds**: weapon, body, metal, glass, wood, and bell impacts. Source: <https://kenney.nl/assets/impact-sounds>.
- **Interface Sounds**: menu select, confirm, back, error, open, close, switch, and tick cues. Source: <https://kenney.nl/assets/interface-sounds>.
- **Casino Audio**: chips and dice used by the Casino Car. Source: <https://kenney.nl/assets/casino-audio>.
- **Digital Audio**: ability, doctrine-break, and steam/electrical accents. Source: <https://kenney.nl/assets/digital-audio>.

The shared included license copy is `assets/audio/kenney/KENNEY_CC0_LICENSE.txt`. Brassline also synthesizes its looping wheel-and-boiler ambience at runtime; that generated waveform contains no third-party recording.

## Original faction emblems

`assets/ui/faction_crew.png` and `assets/ui/faction_guard.png` were generated specifically for this prototype with OpenAI's built-in image-generation tool and resized to 256 x 256 PNGs with preserved alpha.

Crew prompt: original Brassline heist crew emblem; cogwheel around a locomotive wheel with crossed flintlock pistols; hand-painted tactical-RPG icon; weathered brass and oxidized teal; centered, front-facing, no text or watermark.

Guard prompt: original Rail Marshal shield; vertical railway track, mechanical eye, and crown-like steam valves; hand-painted tactical-RPG icon; gunmetal, copper, and crimson; centered, front-facing, no text or watermark.

No paid art assets are used in this build. The custom emblem prompts above were run in built-in image-generation mode; no user-supplied image was used as input.

## Original inventory item atlas

`assets/ui/items/brassline_item_atlas.png` was generated specifically for Brassline with OpenAI's built-in image-generation tool. It contains four isolated, transparent-background UI objects: a weathered leather Medkit, an articulated iron-and-brass Limb Brace, a blackened-steel Clockwork Grenade, and a cobalt Focus Tonic vial.

Prompt summary: exact 2x2 transparent inventory atlas; grounded Victorian steampunk train-heist style; realistic hand-painted material rendering; worn leather, blackened iron, aged brass, cobalt glass; no text, border, or scene background. It was generated from text only with no reference image, then integrated as four Godot `AtlasTexture` regions. The original generated file remains in the Codex image cache; the project-bound copy is the file listed above.

## Original weathered carriage material

`assets/environment/generated/weathered_iron_plate.png` was generated specifically for Brassline with OpenAI's built-in image-generation tool. It is retained as an optional source asset; tactical metal surfaces now use broad painted values and modeled trim to avoid texture shimmer at carriage scale.

Prompt summary: seamless straight-on blackened Victorian iron plate material with shallow seams, aged-brass rivets, scratches, soot, oil, and restrained oxidation; no objects, text, perspective, glow, or bright color. It was generated from text only with no reference image. The original remains in the Codex image cache; the project-bound copy is the file listed above.

## Original modeled weapons and functional furniture

The six weapon silhouettes in `scripts/weapon_model.gd` and the trunks, dining settings, lockers and freight-crate details in `scripts/environment_art.gd` are original code-built mesh geometry created for Brassline. No outside mesh or paid asset was used for these additions. Existing Quaternius character rigs and Kenney environmental kit assets remain under their included CC0 licenses. `scripts/weapon_support_pose.gd` poses the existing character arm and finger bones; it does not replace the source character assets.

