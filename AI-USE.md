# AI use — Gear Shift

Running list for Retro Gaming Dad. Update this when the tools or the shipped files change. The itch / GitHub sentence is drafted in `JAM-CHECKLIST.md`. Do not publish until Retro Gaming Dad says so.

## Stage 1 (2026-11-18) — core driving

- **Code.** Stage 1 (`index.html`, `src/`, this note, and the Stage 1 README section) was written with Grok Build (xAI Grok). Retro Gaming Dad's design doc, asset plan, and jam checklist were the spec. No parallel design was added.
- **Planning docs.** `GAME-DESIGN-DOC.md`, `ASSETS-PLAN.md`, `JAM-CHECKLIST.md`, and the Grok prompt files were already in the folder before this stage. They were not rewritten here.
- **Art.** No generated images, meshes, or textures ship in this build. The car, road, walls, and infield boxes are grey-box primitives built in code with Three.js. They were not exported, so nothing was added to `D:\RetroGamingDad-Assets` or `ASSET-INDEX.csv`.
- **Audio.** No audio files. The engine tone and the shift blip are procedural Web Audio oscillators in `src/game.js`. Mute (M) sets the master gain to zero.
- **Libraries.** Three.js 0.160.1, official MIT build, is vendored in `vendor/three.min.js` with `vendor/LICENSE`. Copyright 2010-2023 three.js authors. It was downloaded from the official package, not generated.
- **Fonts.** System fonts only. No font files.

## Stage 2 (2026-11-18) — gear and shift mechanic

- **Code.** Stage 2 (`index.html`, `src/basis.js`, `src/car.js`, `src/track.js`, `src/game.js`, the Stage 2 README section, and this note) was written with Grok Build (xAI Grok). Retro Gaming Dad's design doc, asset plan, and jam checklist were the spec. The test loop was widened and given a jump, a Flip lane, and a short ceiling. The three named tracks were not started.
- **Art.** No generated images, meshes, or textures. The car, road, jump, gate, and ceiling are still grey-box primitives in code. The only new shipped picture is a hand-authored 32×32 tab icon (amber chevron, cyan notch), written in Python, not by an image model. Library original: `D:\RetroGamingDad-Assets\2D\UI\gear-shift-favicon-v1.png`, license `D:\RetroGamingDad-Assets\Licenses\gear-shift-favicon-v1.txt`, index row project `GearShift`, date 2026-11-18. Game copies: `favicon.png`, `favicon.ico`, and `assets/ui/`.
- **Audio.** Still no audio files. The engine tone, the shift clunk, and the gravity whoosh are procedural Web Audio in `src/game.js`. Mute (M) sets the master gain to zero.
- **Libraries and fonts.** Unchanged from Stage 1. Three.js 0.160.1 MIT build. System fonts only.

## Stage 3 (2026-11-18) — tracks

- **Code.** Stage 3 (`index.html`, `src/input.js`, `src/track.js`, `src/game.js`, the Stage 3 README section, and this note) was written with Grok Build (xAI Grok). Retro Gaming Dad's design doc, asset plan, and jam checklist were the spec. The test loop was replaced with Warm-Up Yard, Coastal Switchback, and Skyway Split. `src/basis.js` and `src/car.js` were not retuned. AI rivals, cup flow, and shift-effect particles were not started.
- **Art.** No new generated images, meshes, or textures. Roads, walls, gates, water, cliffs, and city blocks are grey-box primitives in code. Nothing new was added to `D:\RetroGamingDad-Assets` or `ASSET-INDEX.csv`. The Stage 2 tab icon is unchanged.
- **Audio.** Still no audio files. The engine tone, the shift clunk, and the gravity whoosh stay procedural Web Audio in `src/game.js`. Mute (M) toggles the master gain.
- **Libraries and fonts.** Unchanged from Stage 1. Three.js 0.160.1 MIT build. System fonts only.

## Controller pass (2026-11-18) — gamepad and Controller Settings

- **Code.** The controller pass (`src/input.js`, `src/controller.js`, `src/game.js`, `index.html`, the controls section of `GAME-DESIGN-DOC.md` and `GAME-DESIGN-DOC.html`, the README controller notes, and this note) was written with Grok Build (xAI Grok). Retro Gaming Dad's design doc, asset plan, and jam checklist were the spec. This is the gamepad slice of Stage 7, pulled forward. Stage 4 was a later pass. The menu and touch work landed in the Stage 7 section below. Stage 3 tracks, keys 1 / 2 / 3, and R still work.
- **Art.** No generated images, meshes, or textures. The gear button is an inline SVG in `index.html`, not a file, so nothing was added to `D:\RetroGamingDad-Assets` or `ASSET-INDEX.csv`. The Stage 2 tab icon is unchanged.
- **Audio.** Still no audio files. Vibration uses `gamepad.vibrationActuator` when the pad has one. The engine tone stays procedural Web Audio.
- **Libraries and fonts.** Unchanged. Three.js 0.160.1 MIT build. System fonts only. No new dependency for the Gamepad API.

## Stage 4 (2026-11-18) — shift effects

- **Code.** Stage 4 (`index.html`, `src/game.js`, `src/track.js`, the Stage 4 README section, and this note) was written with Grok Build (xAI Grok). Retro Gaming Dad's design doc, asset plan, and jam checklist were the spec. The juice is the gear slam, camera kick, field-of-view punch, palette lerp, chromatic fringe, speed lines, gate prompts, the gear-1 plant, fail messages, the Flip camera follow, and the first-time Warm-Up card. Gear speeds, gravity, the 0.32 second shift, Flip latch, safe downshift, and handling were not retuned. AI rivals were not started.
- **Art.** No generated images, meshes, or textures. Speed lines and the fringe are drawn in code. Nothing new was added to `D:\RetroGamingDad-Assets` or `ASSET-INDEX.csv`. The Stage 2 tab icon is unchanged. The gear button is still the inline SVG from the controller pass.
- **Audio.** Still no audio files. The engine tone, the shift clunk, and the gravity whoosh stay procedural Web Audio in `src/game.js`. Mute (M) toggles the master gain. New shift, landing, Flip, and wall hits call the rumble helper added in the controller pass.
- **Libraries and fonts.** Unchanged. Three.js 0.160.1 MIT build. System fonts only, including Impact for the gear numeral and the gate prompts.

## Stage 5 (2026-11-18) — AI rivals and time trial

- **Code.** Stage 5 (`src/ai.js`, `src/save.js`, `src/game.js`, `src/track.js`, `index.html`, the Stage 5 README section, and `_logs/stage5-20261118-rivals-trial.md`) was written with Grok Build (xAI Grok). Retro Gaming Dad's design doc, asset plan, and jam checklist were the spec. This pass adds Time Trial with a best-run ghost and medals, Quick Race, the three-heat Arcade Cup, four named rivals, position plates, and `gearshift_v1` bests, ghosts, medals, cup results, and unlocks. The finish pass corrected the Coastal shortcut lateral offset, retuned the medal table from driven laps, shrank the nameplates, and moved the F2 chip off the time panel. Gear speeds, gravity, the 0.32 second shift, Flip latch, and handling were not retuned. Stage 6 (juice and audio) was not started.
- **Art.** No generated images, meshes, or textures. Rivals use the same grey-box car body in flat colors. Nameplates are canvas sprites drawn in code. Nothing new was added to `D:\RetroGamingDad-Assets` or `ASSET-INDEX.csv`.
- **Audio.** Still no audio files. The engine tone stays procedural Web Audio in `src/game.js`.
- **Libraries and fonts.** Unchanged. Three.js 0.160.1 MIT build. System fonts only.

## Stage 6 (2026-11-19) — juice and audio

- **Code.** Stage 6 (`src/audio.js`, `src/game.js`, `src/controller.js`, `index.html`, the Stage 6 README section, this note, and `_logs/stage6-20261119-juice-audio.md`) was written with Grok Build (xAI Grok). Retro Gaming Dad's design doc, asset plan, and jam checklist were the spec. Gear speeds, gravity, the 0.32 second shift, Flip latch, medal times, and cup points were not retuned. The full menu, touch, and the rest of Settings are the Stage 7 section below.
- **Art.** No new generated images or meshes. Exhaust, tire smoke, and landing dust are Three.js instance boxes in code. Bloom is a CSS overlay. Nothing new was added to the 2D or 3D library folders.
- **Audio.** Original Retro Gaming Dad tones. The live engine, SHUNK, whoosh, stingers, and four-layer theme are Web Audio in `src/audio.js`. WAV snapshots of those tones were synthesized with a Node PCM writer, saved first to `D:\RetroGamingDad-Assets\Audio\` with `Licenses\gear-shift-audio-v1.txt`, indexed as project `GearShift` on 2026-11-19, then copied to `assets/audio/`. No third-party samples and no rips.
- **Libraries and fonts.** Unchanged. Three.js 0.160.1 MIT build. System fonts only.

## Stage 7 (2026-11-19) — menus, settings, gamepad, and mobile

- **Code.** Stage 7 (`index.html`, `src/game.js`, `src/controller.js`, `src/input.js`, `src/touch.js`, `src/ai.js`, `src/audio.js`, the Stage 7 README section, `GAME-DESIGN-DOC.md`, `GAME-DESIGN-DOC.html`, this note, and `_logs/stage7-20261119-menus-mobile.md`) was written with Grok Build (xAI Grok). Retro Gaming Dad's design doc, asset plan, and jam checklist were the spec. The existing Controller Settings and `settings.audio` rows were merged into Settings tabs (Audio / Video / Controls). F2 still opens Controls. Gear speeds, gravity, the 0.32 second shift, Flip latch, medal times, and cup points were not retuned. Saves still merge into `gearshift_v1`.
- **Art.** The Gear Shift logo is a hand-authored SVG, not an image model. Library original: `D:\RetroGamingDad-Assets\2D\UI\gear-shift-logo-v1.svg`, license `D:\RetroGamingDad-Assets\Licenses\gear-shift-logo-v1.txt`, index row project `GearShift`, date 2026-11-19. Game copy: `assets/ui/gear-shift-logo-v1.svg`. How to Play diagrams are inline SVG in the page. The gear button stays the inline SVG from the controller pass.
- **Audio.** No new audio files. Volume sliders snap to steps of 5 so the bar and the label match. A pad press tries to resume the audio context. If the browser still holds it, a small line asks for a key, click, or tap.
- **Libraries and fonts.** Unchanged. Three.js 0.160.1 MIT build. System fonts only. The logo uses Impact, which is already a system face in the HUD.

## Stage 8 and Stage 9 (2026-11-20) — polish and itch packaging

- **Code.** The first part of Stage 8 (Flip shortcuts on Warm-Up and Skyway, Flip Fritz roll fix, Skyway ceiling edge assist, FLIP prompt timing, quality tuning) was written with Grok Build. Grok Build ran out of usage before Stage 8 finished, so the rest of Stage 8 and all of Stage 9 were finished with AI assistance (Grok Bot) editing the files directly: medal retune, credits and tutorial copy, README, LICENSE, ATTRIBUTION, itch page draft, and the jam zip. Retro Gaming Dad directed and approved each step.
- **Art.** The itch cover (630×500) and screenshots are captures of the game itself (in-engine renders with a text overlay), not image-model output.
- **Audio.** No new audio.

## Disclosure text that matches this stage

Gear Shift was made by Retro Gaming Dad with AI assistance. I directed the design, played and approved the work, and made the final decisions. The code was written with Grok Build and other AI assistance (Grok Bot), which I reviewed and tested. The car, rivals, and three circuits are code primitives. The logo and icon are hand-authored. Engine, music, and sound effects are synthesized in the browser with Web Audio. The cover and screenshots are captures of the game. Three.js is credited in the README and `vendor/LICENSE`. No third-party copyrighted characters or commercial music are used.

Game Off asks for this note so players can see how the game was made. Using AI does not change eligibility.

## v1.0.4 (2026-11-23) — music layers, speed feel, Flip signs

- **Audio.** The v1.0.4 music layers (drums, bass, lead, flip) and the Flip and final-lap stingers are synthesized in code in `src/audio.js`. No third-party audio and no downloaded samples. WAV renders of those parts were made with the same Web Audio synthesis and saved under `D:\RetroGamingDad-Assets\Audio\GearShift\`. The game does not load those files.

If a later change adds generated art or audio, name the tool in a new dated section here before that file is treated as final.
