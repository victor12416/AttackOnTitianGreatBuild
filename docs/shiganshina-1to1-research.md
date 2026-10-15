# Shiganshina 1:1 blueprint research basis

## Scope and coordinate convention

The first detailed build sheet is Shiganshina District, the southern Wall Maria outcrop. The model uses **1 Minecraft block = 1 metre** in the horizontal plane, integer X/Z block coordinates, and a separately selectable ground Y. The starting footprint is 700 m wide with a 530 m gate-to-gate span; the viewer treats that span as total district depth for the first parametric outline. This is an explicit fan-reconstruction assumption. The existing all-walls schematic is not a 1:1 build plan and must not generate one map cell for every square metre.

Keep the district as a local, high-detail sheet. The larger wall system is context geometry only. Render the walls as vector/parametric geometry at overview zoom, and resolve editable block placements only in the visible build area. Preserve the designated inner face of the main ring as the protected boundary; wall thickness extends outward from that boundary so wall construction does not reduce the modeled interior radius.

## Evidence and confidence

| Fact | Working value | Confidence / use |
| --- | ---: | --- |
| Wall Maria radius from the central point | about 480,000 m | Approximate anime reference figure; overview only |
| Wall Rose radius | about 380,000 m | Approximate anime reference figure; overview only |
| Wall Sina radius | about 250,000 m | Approximate anime reference figure; overview only |
| Clear radial intervals shown between Maria/Rose and Rose/Sina | about 100,000 m and 130,000 m | Approximate; do not derive a district-scale map from the broad diagram |
| Wall height | about 50 m | Well-attested setting value; useful as a 50-block default, still editable |
| Shiganshina location | south of Wall Maria | Canon location |
| Four outer districts per major wall | cardinal positions | Canon layout convention; district names/directions vary by wall |
| Gate-to-gate span | about 530 m in a fan-made 1:1000 scene-based model | Useful district-scale reconstruction, not canon or official survey |
| District outer wall/gates/building coordinates | no authoritative construction plan located | Must be authored from calibrated anime/manga frames or user-provided plans; never present generated placements as canon |

The official [Attack on Titan portal’s special gallery](https://aot-portal.com/special-gallery/info/) publishes “Walls” and “broad-scale illustration of the human domain” information cards. The scale figures commonly read from the anime’s introductory card are approximate. The broad territorial illustration is explicitly described by secondary references as not accurately depicting the size of its towns and Walls, so its drawn proportions must not be treated as a survey map.

A modeler’s [1:1000 greyboard reconstruction](https://www.reddit.com/r/ShingekiNoKyojin/comments/g5wnqu/greyboard_model_of_shiganshina_in_scale_11000/) reports about 53 cm between gates (about 530 m) and uses a 100 × 70 cm board. The board translates to a 1,000 × 700 m modeling envelope, not a verified district boundary; using its 700 m width and 530 m gate span as viewer defaults is an explicit, editable reconstruction. The modeler says the dimensions were estimated from several anime scenes, and notes proportion inconsistencies. This is more district-specific evidence than the broad territory diagram, but remains fan interpretation. A separate [fan calculation](https://www.reddit.com/r/attackontitan/comments/14ki12z/) derives 11.47 × 8.87 km from the broad schematic and wall-tile assumptions; that result conflicts sharply with the scene-based model and is not used as the viewer default.

The [Shiganshina overview](https://www.attackontitan.nl/en/world/shiganshina/) describes it as one of the four districts jutting from Wall Maria and places it in the south. The [Wall Maria overview](https://www.attackontitan.nl/en/world/wall-maria/) describes the outer/inner gate events. In the story, the Shiganshina outer gate in the projecting district and the Wall Maria inner gate are separate breach points. The model should represent gate openings as parts of their respective wall paths, not detached objects and not gaps that silently shift the protected circle.

## Geometry rules for the viewer

1. Keep wall radii and district size in metres/blocks, not screen pixels. Zoom and pan must not change measurements.
2. Represent main-wall protected radius by an explicit reference face (default: inside face). Apply thickness outward from that reference. Label any alternate centerline/outside-radius convention.
3. Model a district as an editable outcrop attached continuously to the main wall boundary. Its side walls and rounded outer end must join without a wedge gap or a one-cell tangency. Do not close its land polygon across the interior connection.
4. Place the two Shiganshina gate assemblies on their correct wall paths: district outer gate on the projecting end; Wall Maria inner gate on the main ring. Each opening has a lintel/arch/tower structure, and the rest of each wall continues on both sides.
5. Treat gate widths, wall thickness, wall profile, district footprint, streets, canals, building footprints, and elevations as configurable until a sourced view can calibrate them. Show source/confidence metadata with each value.
6. Use block coordinate sheets/tiles for construction. An 8.87 km × 11.47 km estimate contains about 101 million horizontal cells before buildings; exporting or allocating an array for every ground cell is wasteful. Store sparse structure placements and render only the viewport.
7. A 1:1 coordinate system does not make the town’s unknown block layout canonically accurate. The blueprint needs a calibrated reference layer and authored feature layers, with estimated and confirmed placements visibly distinguished.

## Reference work still needed

Before claiming a complete accurate build blueprint, calibrate the district outline, gates, roads, canals, key landmarks, and building clusters against source frames. Use repeated fixed landmarks to correct for perspective, and record the frame/episode/page plus estimated pixel-to-metre scale and confidence. The outer wall’s broad radius can remain a context measurement; it should not force the entire 480 km radius map into a high-detail build sheet.
## Current implementation

The draft viewer now has a 1 block = 1 metre coordinate grid, parametric district and ring geometry, separate inner/outer gate openings, wall-course selection, sparse block placement and CSV import, reference-image scale/translation, and tile CSV export. Tile export rasterizes only a selected 64/128/256-block square at integer coordinates; it never allocates the entire ring or district footprint. The inner circular wall is placed with its centerline at radius + half-thickness, keeping the selected protected inner-face radius fixed.

The viewer is ready for functional testing of coordinate math and tile output. A visual browser check was unavailable in this environment, so the next tester should verify pan/zoom behavior, overlay alignment, and the two openings in the actual browser. The house/street plan is still intentionally blank: no authoritative source gives a complete block-level Shiganshina plan, and invented placements would look precise without evidence.
