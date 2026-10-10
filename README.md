# VedaShield Anatomy 3D

Interactive human anatomy built with React, TypeScript, Three.js, React Three
Fiber and Vite. Extracted from [human-anatomy-3d](https://github.com/sheevu/human-anatomy-3d)
with the completed anatomy design and interaction improvements. The existing
healthcare workspace remains at `/`; the anatomy explorer is at `/anatomy`.

## Setup

Use Node.js 22.13 or newer.

```bash
npm ci
npm run dev
```

Open http://localhost:5173/anatomy. Anatomy needs no login, backend or API keys.

```bash
npm run typecheck
npm test
npm run build
npm run preview
```

Production output is in `dist`. No lint configuration is present. GitHub Actions
runs asset tests and the production build on pushes and pull requests.

## Controls and Features

- Click or tap real model groups: selection highlights the organ, fades surrounding
  anatomy, smoothly focuses its geometry and opens an HTML description overlay.
- Hover feedback, name search, six system filters and per-group hide/show controls.
- Focus, isolate, front/back/side views, labels and optional auto-rotation.
- Drag to orbit, wheel/pinch to zoom, right-drag/two-finger drag to pan.
- Full body restores all structures, clears filters and resets the camera.
- Focus the viewport for keyboard controls: left/right arrows orbit, up/down arrows
  pan vertically, plus/minus zoom, R resets and Escape clears selection.
- Desktop, tablet and mobile layouts; reduced-motion transitions; on-demand
  rendering; capped pixel ratio; individual model failures and retry controls.

## Model Coverage and Licenses

Ten selectable merged groups: brain, heart, lungs, liver, stomach, pancreas,
kidneys, intestines, thoracic skeleton and major vessels. A non-selectable external
body provides context. All eleven GLBs total less than 3 MB.

Paired organs, individual ribs, heart chambers, small vessels and microscopic
anatomy are not separate meshes and cannot be selected independently. The skeleton
is a chest assembly, not a complete skeleton. Missing models are not replaced with
procedural organs. Generic educational anatomy is not a patient scan or diagnostic
or surgical tool.

BodyParts3D, copyright The Database Center for Life Science. Existing derived GLBs
retain the source mirror's CC BY-SA 2.1 Japan terms. See
[attribution](public/models/ATTRIBUTION.md) and
[source license](public/models/LICENSE-source.txt). The upstream project grouped,
simplified, transformed and converted these models. The official database now
lists CC BY 4.0; this repository does not relicense the shipped derivatives or
assert a new software license for inherited application code.

For complete structure-level interaction, export optimized models preserving
individual meshes, stable IDs, names, sidedness, system membership and shared
coordinates; then validate anatomy with a qualified reviewer. The upstream raw
OBJ and Z-Anatomy Blender datasets are not bundled here.

## Verification and Hosting

Asset tests check GLB validity, real geometry, bounds, existing manifest hashes,
attribution and size budgets. Development browser checks covered desktop and
mobile mesh picking, ten named selections, orbit, zoom, isolate, visibility,
filters, reset, screenshots and nonblank canvas pixels. Tablet layout, missing
asset retry and simulated graphics-context loss were also checked. Local browser
automation runtimes and screenshots are not bundled.

Static hosting must serve `index.html` for `/anatomy` and `/models/*` as real binary
assets. Vite dev and preview already handle this. The existing healthcare backend
and Wrangler configuration are retained but their production deployment and
healthcare integrations are outside this anatomy validation. The inherited
healthcare bundle has a size warning and is loaded separately from the explorer.
Creating this repository does not deploy the site.
