# Shiganshina 1:1 blueprint research basis

## Scope and coordinate convention

The first detailed build sheet is Shiganshina District, the southern Wall Maria outcrop. The model uses **1 Minecraft block = 1 metre** in the horizontal plane, integer X/Z block coordinates, and a separately selectable ground Y. The existing all-walls schematic is not a 1:1 build plan and must not generate one map cell for every square metre.

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
| Shiganshina district footprint | no authoritative numeric dimensions located | Must remain an estimate pending direct source calibration |
| District outer wall/gates/building coordinates | no authoritative construction plan located | Must be authored from calibrated anime/manga frames or user-provided plans; never present generated placements as canon |

The official [Attack on Titan portal’s special gallery](https://aot-portal.com/special-gallery/info/) publishes “Walls” and “broad-scale illustration of the human domain” information cards. The scale figures commonly read from the anime’s introductory card are approximate. The broad territorial illustration is explicitly described by secondary references as not accurately depicting the size of its towns and Walls, so its drawn proportions must not be treated as a survey map.

A fan calculation proposes a district envelope around 11.47 km deep by 8.87 km wide by measuring schematic illustrations and assuming wall-tile dimensions. This is an inference, not an official dimension, and its inputs are not independently established. It may be offered as an editable **provisional footprint preset**, clearly marked “fan estimate,” never locked as ground truth. See the calculation and assumptions in [the fan analysis](https://www.reddit.com/r/attackontitan/comments/14ki12z/).

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
