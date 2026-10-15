# Shiganshina 1:1 Blueprint

A browser-based, block-coordinate blueprint editor for planning Shiganshina District one construction area at a time.

## Scale and coordinates

- Horizontal scale is **1 Minecraft block = 1 metre**. Map coordinates are integer X/Z block coordinates; course and ground elevation determine Y.
- The map origin is the center of Wall Maria at **X=0, Z=0**. East is +X and south is +Z. Shiganshina is modeled at the south edge of the approximate Wall Maria radius.
- The editable Wall Maria radius starts at 480,000 blocks. This is an approximate anime reference figure. The viewer treats it as the **protected inner face** by convention, because the source does not say whether the quoted radius is measured at the inside, centerline, or outside of the wall.
- The district starts with a **700-block width envelope** and a **530-block gate-to-gate span**. These are estimates based on a fan-made physical model at 1:1000 scale: its maker reports 53 cm between gates on a 100 × 70 cm display board. That provides a better district-specific working reference than the much broader wall map, but it is not official survey data. The viewer explicitly assumes the gate span is also the district depth.
- Wall thickness and gate opening width are editable placeholders. Thickness is centered outward from the protected inner face, so it does not reduce the selected protected radius.
- The first-pass outcrop shape is an editable straight-sided approach with a half-round outer end. Its exact silhouette is not canonically measured.

The viewer separates known relative placement and gate relationships from estimated measurements and unknown city details. It does not claim that streets or building footprints are canonically measured. See [the research notes](docs/shiganshina-1to1-research.md) for source links and confidence notes.

## Build workflow

1. Start with **Fit district**. Pan by dragging and zoom at the cursor with the mouse wheel. **Go to coordinate** moves directly to a known X/Z. Click the map to inspect a block coordinate.
2. Load a top-down reference image under **Reference overlay**. Set its width in metres and center X/Z to align it against known coordinates. The image stays local in the browser session.
3. Adjust district width/span, protected radius, wall thickness, and gate width as evidence improves. They are editable values, not locked canon dimensions.
4. Select a vertical course. Course 0 is the wall foundation at the selected ground Y; courses 1 through the configured height build the wall; the last course is the cap.
5. Select **Enable placement**, zoom to at least 1 pixel per block, then click to place one block at the displayed X/Y/Z. Shift-click removes it. The selected block ID is used for placements and generated wall tiles.
6. Choose a 64, 128, or 256-block tile and select a point in that area. **Export wall + blocks in tile** writes a sparse CSV for the selected Y course. The wall is rasterized to integer block coordinates and leaves both gate openings clear. You can import a CSV with columns `x,y,z,block`.
7. Download the project JSON regularly to back up local placement data.

Saved placements are held in the current browser's local storage. They do not sync between devices. The parametric Wall Maria curve is drawn efficiently at any zoom; the app does not allocate a 480 km square grid.

## Test checklist

- Fit the district and confirm the canvas remains responsive. Zoom from the wall context to individual blocks; pan and check cursor coordinates.
- Confirm defaults show the fan-model estimates: width envelope 700, gate-to-gate span 530, radius 480,000.
- Export the tile centered on the inner gate. It should include wall blocks beside the opening, omit the gate opening, and keep the protected interior radius clear.
- Export a tile around the outer gate. The half-round district wall should stop at the gate opening.
- Change the course and ground Y. Confirm generated CSV Y values equal ground Y plus the selected course.
- Place a block at 1:1 zoom, shift-click to remove it, import a placement CSV, and reload to confirm local persistence.
- Load a reference image, adjust width/opacity/center, and confirm it follows pan and zoom.
- Change the dimensions and wall thickness. Confirm the preview updates and protected radius remains fixed.

## Known limitations

- There is no official block-level Shiganshina survey or complete street/building plan. Exact district dimensions, wall-face convention, wall thickness, gate width, street layout, canals, elevations, and building coordinates remain uncertain or unmeasured.
- The 530 m gate spacing and 700 m board envelope come from a fan-made 1:1000 model based on anime scenes. They are an explicit starting reconstruction, not canon dimensions. The often-repeated 11.47 km × 8.87 km proposal comes from a different fan calculation over a broad schematic and is not used as the district default.
- The reference overlay supports scale and translation, but not rotation or perspective correction. Calibrate against multiple known landmarks; a single perspective screenshot cannot establish a complete survey.
- Gates are shown as openings on the two distinct wall paths. Detailed gatehouses, towers, roads, building footprints, and interiors must be authored from calibrated references; the viewer does not invent them as canon.
- Minecraft terrain Y varies. Set ground Y for each build area before exporting its course.

