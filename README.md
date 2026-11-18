# Biostage

A browser-based animation suite for scientists: load protein structures, build molecules, add lipid bilayers and tight junctions, drop in papers and lift figures off the page, and animate everything with Manim-style labels, arrows, titles and LaTeX equations on an always-visible timeline.

Everything lives in a single `index.html`, with no build step.

## Run it

- **Locally:** open `index.html` in a modern browser (Chrome, Edge, Firefox or Safari). An internet connection is needed for the 3D engine, the PDF reader and the equation renderer, which load from public CDNs.
- **GitHub Pages:** push this folder to a repository, then in **Settings → Pages** choose *Deploy from a branch*, pick `main` and `/ (root)`, and save. The app appears at `https://<you>.github.io/<repo>/`.

On GitHub Pages, **Fetch** (by PDB ID) downloads structures straight from RCSB, and **Save video** downloads normally.

## What's in it

| Thing | What you can animate |
|---|---|
| Structure (`.pdb` / `.cif`, or fetch by PDB ID) | cartoon ↔ atoms, atom size, sticks, ligands, spin, position, scale |
| Molecule (SMILES or presets) | same as structures; geometry is idealised, not energy-minimised |
| Membrane | curvature (flat → vesicle), thermal jiggle, pore radius, tilt |
| Tight junction | gap opening, claudin strand loss, solute leak |
| Paper stack (`.pdf`, `.png`, `.jpg`) | pile → fan/row/grid, focus page, lift page |
| Figure cut-out | lift off the page and land on (and crossfade into) a 3D object |
| Label / Arrow / Title / Equation | write-on, opacity, position, size; labels and arrows pin to residues or objects |
| Camera | orbit, tilt, distance, lens, look-at point |

Click ◇ beside any property to start animating it. After that, changing the property at a new time adds a key. Drag keys on the timeline (Shift = no snapping). Space plays.

## Notes

- Your scene autosaves in the browser (localStorage), and dropped PDFs and images are kept in IndexedDB.
- Video export records in real time to WebM or MP4, depending on the browser.
- Libraries: three.js r128, pdf.js 2.16, MathJax 3, all loaded from CDNs.
