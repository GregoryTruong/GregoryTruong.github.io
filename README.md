# gregorytruong.github.io

My personal website, live at **https://gregorytruong.github.io**.

It's a scroll-driven drive through a neon city at night. Each exit is a chapter: about me, my projects ([Car Depreciation Analyzer](https://github.com/GregoryTruong/car-depreciation), [Stock Report Card](https://github.com/GregoryTruong/stock-report-card)), my toolkit, and how to reach me.

## How it's built
- One `index.html` with no build step and no frameworks.
- The city, road, traffic and rain are drawn on a `<canvas>` with a hand-rolled pseudo-3D projection: each object has a world position `(x, y, z)` and is projected to the screen with `x' = cx + x·f/z`, `y' = horizon + (camHeight − y)·f/z`. Road curves come from bending x by `curv · z²`.
- Scroll speed drives the car's speed, and reaching a new section triggers a speed burst.
- The music and engine sound are synthesized live with the Web Audio API, with no audio files.

## Updating
Edit `index.html` (on github.com, click the file and then the pencil icon), commit, and GitHub Pages redeploys in about a minute.
