# gregorytruong.github.io

My personal website, live at **https://gregorytruong.github.io**.

It's a scroll-driven late-night drive through Saigon. You start parked in a plaza, then each exit is a chapter: about me, my projects ([Car Depreciation Analyzer](https://github.com/GregoryTruong/car-depreciation), [Stock Report Card](https://github.com/GregoryTruong/stock-report-card)), the math behind the site, my toolkit, and how to reach me. At the end you can take the wheel and drive for as long as you like.

## How it's built
- One `index.html` with no build step and no frameworks.
- The city, road, traffic and rain are drawn on a `<canvas>` with a hand-rolled pseudo-3D projection: each object has a world position `(x, y, z)` and is projected to the screen with `x' = cx + x·f/z`, `y' = horizon + (camHeight − y)·f/z`. Road curves come from bending x by `0.0022 · κ · z²`, where `κ(s) = 0.9 sin(s/110) + 0.25 sin(φ²s/110)` mixes two waves with an irrational ratio (φ² is the golden ratio squared), so the road never repeats. Street tower heights follow `14 + 81·{nφ}`.
- Scroll speed drives the car's speed, and reaching a new section triggers a speed burst.
- The "Under the hood" section explains these equations, and "Show the math on the road" draws them live.
- The music and engine sound are synthesized live with the Web Audio API, with no audio files.

## Updating
Edit `index.html` (on github.com, click the file and then the pencil icon), commit, and GitHub Pages redeploys in about a minute.
