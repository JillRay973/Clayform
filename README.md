# Clayform

A digital sculpting app that runs entirely in the browser: no install, no build step, one HTML file. It works with a mouse, a trackpad, or an iPad with Apple Pencil (pressure supported, palm ignored while drawing).

**Live demo:** turn on GitHub Pages for this repo (see below) and it'll be at `https://<your-username>.github.io/clayform/`.

## Features

**Sculpting**
- 15 brushes: Standard, Clay, Inflate, Layer, Blob, Crease, Smooth, Flatten, Planar, Pinch, Move, Snake Hook, Nudge, Paint, Mask
- Add / Subtract (hold Alt), quick Smooth (hold Shift)
- 4 falloff curves, Lazy stroke stabilizer
- Symmetry on X / Y / Z plus radial symmetry (3–16)

**Geometry**
- Starts light (~3k faces); Divide adds Loop-subdivision levels up to ~865k faces
- Step down and back up through levels without losing detail
- Voxel Remesh: even triangles, fuses separate parts together; optional "keep detail" projection
- Insert spheres, cubes, cylinders and tori onto the model

**Retopology**
- Draw quads point by point on the sculpt surface; drag points to slide them along it
- Shift + 2 points (or the Attach toggle) adds a quad to the nearest open edge
- Insert edge loops anywhere along a ring of quads (with preview); Alt-click removes a loop
- Divide quads, Relax, Mirror +X → −X
- Auto quads: one-click all-quad mesh at a target face count
- Export the quad mesh as OBJ, or use it as the new sculpt base and project the old detail back onto it

**Masking & deformation**
- Paint masks (Ctrl/⌘), invert, clear, blur, sharpen, grow, shrink, mask by cavity
- Whole-mesh smooth, inflate/deflate, surface noise, mirror, unify (all mask-aware)

**Polypaint & display**
- Paint vertex color, fill / clear (mask-aware)
- 6 materials, wireframe, flat shading, turntable, front/side/top/back views

**Files**
- Import OBJ and STL
- Export OBJ (keeps polypaint as vertex colors), binary STL for 3D printing, PNG snapshots
- Full undo / redo, including remesh and insert

## Controls

| Input | Action |
|---|---|
| Drag on the model | Sculpt |
| Drag on the background | Orbit |
| Right-drag | Pan |
| Mouse wheel / pinch | Zoom |
| Alt | Flip Add / Subtract |
| Shift | Smooth |
| Ctrl / ⌘ | Mask (Ctrl+click background inverts) |
| 1–9, 0 | Brushes |
| [ ] | Brush size |
| X | X symmetry |
| L | Lazy stroke |
| D / Shift+D | Up / down a subdivision level |
| Ctrl+D | Divide |
| R | Remesh |
| W, F, T | Wireframe, frame model, turntable |
| Q | Retopo mode |
| E | Retopo: toggle edge-loop tool |
| A | Retopo: toggle Attach |
| Ctrl / ⌘ + Z | Undo (Shift for redo) |

On iPad: one finger or the Pencil on the model sculpts, one finger on the background orbits, and two fingers always pan and zoom.

## Running it

Open `index.html` in a modern browser (Chrome, Edge, Safari, Firefox). It needs an internet connection the first time because it loads three.js from a CDN.

### Publish with GitHub Pages
1. Push this repo to GitHub.
2. In the repo, go to **Settings → Pages**.
3. Under **Build and deployment**, set **Source** to *Deploy from a branch*, pick `main` and `/ (root)`, and save.
4. After a minute the site is live at `https://<your-username>.github.io/<repo-name>/`.

## Built with
- [three.js](https://threejs.org/) (MIT) for rendering
- [three-mesh-bvh](https://github.com/gkjohnson/three-mesh-bvh) (MIT) for fast ray casting and brush queries

All sculpting, remeshing, subdivision and retopology code is original and lives in `index.html`.

Clayform is an independent project and is not affiliated with or endorsed by Maxon (ZBrush) or Autodesk (Maya).

## License
MIT. See [LICENSE](LICENSE).
