# Climbing Hold Generator

A static, client-side climbing-hold generator designed to run on GitHub Pages.

## Features

- Parametric 3D preview
- Hold presets: jug, crimp, sloper, pinch, pocket, volume
- Live controls for width, height, depth, edge/lip, undercut, roundness, pocket size, texture, rotation and tilt
- Optional screw/bolt-hole visuals
- Randomize and reset
- Orbit/zoom/pan 3D viewer
- Client-side STL export
- No backend and no build step

## Run locally

Open `index.html` in a modern browser. If your browser blocks ES modules from `file://`, use any tiny local HTTP server, for example:

```bash
python -m http.server 8000
```

Then open `http://localhost:8000`.

## GitHub Pages

1. Create a new GitHub repository.
2. Upload `index.html` and this README.
3. Go to **Settings → Pages**.
4. Select **Deploy from a branch**, choose `main` and `/ (root)`.
5. Save. GitHub will publish the site.

## Important manufacturing note

The current generator is a **prototype geometry generator**, not a certified climbing-hold CAD system. The STL export includes the visible procedural geometry and hole objects, but the hole geometry is not boolean-subtracted from the base mesh.

Before manufacturing or climbing on a generated hold, inspect the STL in a CAD/mesh tool, make actual watertight boolean cuts, validate wall thickness, mounting geometry and material suitability, and test the finished hold appropriately. Do not use an untested generated hold for climbing.
