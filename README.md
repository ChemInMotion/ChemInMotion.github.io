# Mechanism Lab

A single-page website for storing and viewing chemical reaction mechanisms as animations.

- **3-D view:** ball-and-stick model on a black stage, with CPK colors, half-and-half bonds, ribbed green (forming) and rose (breaking) bonds, glow and halo highlights, δ+/δ− labels and numbered electron-flow arrows.
- **2-D view:** skeletal structure with N/O/P labels, wedge and dash bonds, circled formal charges, lone-pair dots, and atoms that slide between steps.
- **Camera:** auto (planned per step) or interactive (drag to rotate or pan, scroll to zoom).
- **Tabs:** one tab per mechanism in a collapsible sidebar.

Included mechanism: acid-catalysed hydrolysis of sucrose (4 steps).

## Run it

No build step and no dependencies. Open `index.html` in a browser.

## Publish with GitHub Pages

1. Push this folder to a GitHub repository.
2. Go to **Settings → Pages**.
3. Under **Build and deployment**, choose **Deploy from a branch**, select `main` and `/ (root)`, then save.
4. Your site will appear at `https://<your-username>.github.io/<repo-name>/`.

## Add a mechanism

Open `index.html`, find the line `const MECHS=[sucrose()];`, and add another function that returns an object with:

- `A`: atoms (`id → {el, p:[x,y,z], oh}`)
- `P`: atom positions for each step
- `Bs`: bonds for each step
- `S`: steps (title, description, bonds forming or breaking, glow and halo atoms, δ labels, electron flows, camera preset)

Copy the `sucrose()` function as a template. Each new entry gets its own tab automatically.

## Notes

Geometry is schematic, not energy-minimized, and only hydrogens that take part in a step are drawn. Montserrat loads from Google Fonts; everything else is self-contained.
