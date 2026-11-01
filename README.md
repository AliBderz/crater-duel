# Crater Duel

An artillery duel against a CPU gunner on a destructible hill. Built for **AICODE 67723 · Lab 1 — Build Something Live in 1 Hour**.

**Play it:** https://alibderz.github.io/crater-duel/

Runs entirely in the browser: one `index.html`, no server, no backend, no API keys.

## How to play

- **Elevation** (`←` `→` or the slider): 0° fires flat to the right, 90° straight up, 180° flat to the left.
- **Charge** (`↑` `↓` or the slider): muzzle speed. At 100% and 45° a shell crosses the whole map in still air.
- **Fire** with `Space` or the button. You can also drag on the field to aim.
- **Wind** changes every turn and pushes the shell sideways the whole way. The gauge points the way it blows.
- Every shell digs a crater that stays. Falling into a fresh crater hurts too.
- `M` toggles sound, `H` opens the gun manual.

## What's under the hood

- Procedural terrain from layered value noise, stored as a heightmap so craters are a one-line edit.
- Fixed-step projectile physics with gravity and wind, shared between the live shell and the CPU's simulations.
- The CPU opponent simulates about 1,300 trajectories in the current wind before every shot, picks the closest, then adds a wobble so it can miss (Easy / Normal / Hard set the wobble).
- Sound is synthesized with the Web Audio API (oscillators and filtered noise); nothing is downloaded.
- Particles, screen shake, falling tanks, and a single-file layout that works on phones.

## Deploying

Published with GitHub Pages from the `main` branch, root folder. Push to `main` and the site rebuilds in about a minute.

## Run locally

Open `index.html` in any browser. No build step.
