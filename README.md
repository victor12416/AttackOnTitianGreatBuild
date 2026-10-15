# Shiganshina 1:1 Blueprint

A browser-based, block-coordinate blueprint editor for planning Shiganshina District one construction area at a time.

## Scale and coordinate system

- Horizontal scale is **1 Minecraft block = 1 metre**. All map coordinates are integer X/Z block coordinates.
- The map origin is the center of Wall Maria at **X=0, Z=0**. East is +X and south is +Z. Shiganshina is placed at the south edge of the approximate Wall Maria radius.
- The editable radius starts at 480,000 blocks. This is an approximate anime reference figure. The app treats it as the **protected inner face** by convention, because the source does not say whether the quoted radius is measured at the inside, centerline, or outside of the wall.
- The district starts with an **8,870-block width × 11,467-block depth** fan estimate. These dimensions are not official measurements. Adjust them when better source calibration is available.
- The wall thickness and gate opening width are editable estimates. Thickness is centered outward from the protected inner face, so it does not reduce the protected radius.
- The district outcrop is a parametric rectangle with a half-round outer end. That is a useful editable interpretation of the schematic silhouette, not a surveyed canon map.

The viewer separates the confirmed relative placement of Shiganshina and its two distinct gate locations from estimated measurements and unknown city details. It does not claim that streets or building footprints are canonically measured. See [the research notes](docs/shiganshina-1to1-research.md) for source links and confidence notes.

## Build workflow

1. Start with **Fit district**. Pan by dragging and zoom at the cursor with the mouse wheel. The **Go to coordinate** fields move directly to a known X/Z. Click the map to inspect a block coordinate.
2. Load a top-down reference image under **Reference overlay**. Set its width in metres and center X/Z to align it against known coordinates. The image stays local in the browser session.
3. Adjust the district width/depth, protected radius, wall thickness, and gate width as evidence improves. The footprint and gate widths are intentionally editable.
4. Select the vertical course. Course 0 is the foundation at the chosen ground Y; courses 1 through the configured height build the wall; the last course is the cap. The wall preview changes color by course.
5. Select **Enable placement**, zoom to at least 1 pixel per block, then click to place one block at the displayed X/Y/Z. Shift-click removes a placement. The chosen block ID is used for placements and generated wall tiles.
6. Choose a 64, 128, or 256-block tile and select a point in that area. **Export wall + blocks in tile** writes a sparse CSV for the selected Y course. The wall is rasterized to integer block coordinates and leaves both gate openings clear. You can also import a CSV with columns `x,y,z,block`.
7. Download the project JSON regularly to back up the local placement data.

Saved placements are held in the current browser's local storage. They do not sync between devices. The parametric Wall Maria curve is drawn efficiently at any zoom; the app does not allocate a 480 km square grid.

## Test checklist

- Fit the district and confirm the canvas remains responsive. Zoom from the whole-wall context to individual blocks; pan and verify the coordinates under the cursor move consistently.
- Confirm default values show the **fan-estimate** label: width 8,870, depth 11,467, radius 480,000.
- Export the tile centered on the inner gate. It should include wall blocks beside the opening, omit blocks through the opening, and keep the protected interior radius clear.
- Export a tile around the outer gate. The half-round district wall should stop at the gate opening.
- Change the course and ground Y. Confirm generated CSV Y values equal ground Y plus the selected course.
- Place a block at 1:1 zoom, shift-click to remove it, export/import a placement CSV, and reload the page to confirm local persistence.
- Load a reference image, adjust width/opacity/center, and confirm it follows pan and zoom.
- Change footprint and thickness. Confirm the preview updates and the protected radius remains fixed.

## Known limitations

- There is no official block-level Shiganshina survey or complete street/building plan. Exact district dimensions, wall-face convention, wall thickness, gate width, street layout, canals, elevations, and building coordinates remain uncertain or unmeasured.
- The current reference overlay supports scale and translation, but not rotation or perspective correction. For an accurate plan, calibrate a top-down map or several source frames against multiple known landmarks; a single perspective screenshot cannot establish a complete survey.
- Gate assemblies are shown as openings and marked on the correct wall paths. Detailed towers, doors, roads, building footprints, and interior furnishing plans must be authored from calibrated references; the viewer does not invent them as canon.
- Minecraft terrain Y varies. Set the ground Y for each build area before exporting its course.
