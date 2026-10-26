# Unit 10 Railway – project brief

Paste this into a new conversation (or a new project called "Unit 10 Railway") and attach the as-built drawing of Unit 10 again.

## What it is
A virtual OO-gauge (1:76) model railway built inside an accurate 3D model of my flat, Unit 10. It starts in the living room, then extends to the other rooms, with imaginary tunnels through walls and under fixtures such as the shower tray and kitchen units. I lay the track and run the trains myself; it is not a passive simulation.

## Current version
Published page: https://claude.ai/artifact/1cDaXzmzpCW3XtuM8986z1
(Read it with the Artifact tool to get the full source and build on it.)
- Whole flat traced from the as-built drawing; living room at measured size.
- Two views: child's eye (camera 30–50 cm off the floor, orbiting the track) and bird's eye (top-down plan, living room or whole flat).
- One oval of track in the open floor of the living room, curve radius 0.75 m; a tank engine and two coaches; speed in scale mph.
- Built with three.js 0.160 (ES modules from cdn.jsdelivr.net), one HTML file.

## The flat (Unit 10)
- Living room / kitchen: 7.74 m × 4.44 m, measured from the bathroom wall (kitchen units included) to the outside doors.
- Hall width: 1.4 m (measured).
- Ceiling height: 2.28 m (measured).
- Whole flat about 15 m × 7.3 m (read off the drawing).
- Rooms: living/kitchen, hall with loft hatch, bathroom (bath), en-suite (shower), bedroom 1 (built-in wardrobe), bedroom 2, cupboard, front door at the end of the hall.
- The block at the bottom right of the drawing (bedroom, shower room, cupboard) is Unit 9, not part of my flat.
- Drawing scale is 1:200; in the photo, about 108.3 px = 1 m.

## Decisions made
- The flat, not the room, is the base. Rooms join on shared walls; track belongs to the flat and runs through walls as tunnels.
- Realistic look: real floor, wall and door finishes and my furniture, modelled to measurements (architectural-model level, not photo-real).
- Others must be able to build their own tracks in their own room layouts: a room builder, a track builder, sign-in and saving.
- Hosting: Netlify for the site, Supabase for sign-in (email link) and saved layouts, GitHub for the code. I have Netlify and Supabase accounts.
- Friends can see my flat; no need to hide it.

## Still needed from me
- Living room furniture (non-kitchen: sofa, table etc.) — what is there and roughly where (sizes help).
- Photos of the living room from different corners, plus close-ups of the floor, a wall and a door.
- Supabase project URL and anon (public) key. Never the service_role key.

## Kitchen units (from hand-measured sketch, 2026-10-24)
U-shaped kitchen in the back-left corner of the living room/kitchen, against the real back wall and left wall. All measurements in cm on the sketch, confirmed/read as plan-view (top-down) lengths, converted to metres in the scaffold. Box footprints only, not real unit models — placed so track can be routed clear. Needs checking against photos before treating as exact.

- Left wall run: 3.62 m of worktop from the back-left corner, 0.6 m deep, then 0.82 m left clear before the front-left corner.
- Tall larder/fridge unit at the back-left corner, 0.45 m deep.
- Front wall run: 2.6 m of worktop from the front-left corner, 0.6 m deep.
- Doorway gap: 1.8 m clear from the end of that run to the corner of the kitchen (confirmed: this is the distance from the doorway to the kitchen corner).
- Peninsula (the kitchen's "right wall", closing the U): 3.5 m run from the back wall, 0.6 m deep, starting at the corner of the kitchen.
- Cupboard/freezer/cupboard tower near the back end of the peninsula, ~0.9 m wide.
- Worktop height assumed 0.9 m, tall units assumed 2.0 m (not from the sketch — standard values, ceiling is 2.28 m so plausible).

Track in the scaffold was rotated 90° and moved into the open floor east of the peninsula (clear of both the units and the doorway gap) to make room for this.

## Living room furniture + kitchen corrections (from hand-measured sketch, 2026-10-24, second pass)

Confirmed with George/me on 2026-10-24. These correct/extend the kitchen section above and add the first living-room furniture (previously listed as "still needed").

- **Table**: 125cm × 75cm. Gap from the table to the kitchen worktop edge is 75cm.
- **Sofa**: L-shaped. Total length along the wall is 300cm. The piece sticking out (the return/chaise) is 195cm × 90cm. The piece running along the wall is 210cm × 108cm.
- **Doorway-side cupboard run** (previously under-specified as "~0.9m wide tower"): from the doorway, 100cm clear, then a cupboard (84cm), a fridge/freezer (103cm), another cupboard (84cm), then 170cm clear to the L-section of the sofa. Total run ≈ 541cm — **too long to fit the 4.44m room depth as currently modelled, so this is not the same wall as the existing "left wall run"/kitchen worktop. Placement (which wall) needs confirming before updating the 3D scene — see question to George/Neil below.**
- **Peninsula/right-side cupboard correction**: the unit previously modelled as a tall tower (cupboard/freezer/cupboard, ~0.9m wide, 2.0m tall) at the back end of the peninsula is wrong — it's actually a **long, low cupboard run**, 360cm wide, worktop height (not tall-unit height), positioned 82cm out from the kitchen worktop and 100cm from the table. This likely supersedes/corrects the earlier "peninsula 3.5m run + separate tower" reading — needs reconciling against the 3D model.

**Room size correction (2026-10-24, third pass)**: the original 7.74m × 4.44m was only approximate and didn't include the entrance area. Confirmed overall room size is **437cm × 891cm** (4.37m × 8.91m). The 891cm long wall is the doorway → cupboard/freezer/cupboard → sofa wall: 100 + 84 (cupboard) + 103 (freezer) + 84 (cupboard) + 170 + 300 (sofa run) + 15 + 35 = 891cm, confirmed as a direct sum by George. The gap between the right-hand wall and the room entrance is 177cm.

**Resolved (simplified overview sketch, 2026-10-24, fourth pass)**: the room is **not a simple rectangle** — it's notched. Reading the sketch (origin at the bottom-right corner, +X left, +Y up the page):
- Right wall: 891cm, straight, running from bottom-right corner to top-right corner. This is the wall the doorway/cupboard/freezer/cupboard/sofa run (confirmed sum above) is measured along — labelled "Cupboard" (lower) then "Sofa" (upper) going up this wall.
- Top wall: 437cm (the overall width), from top-right corner to top-left corner.
- Left wall: straight, from top-left corner down to the kitchen's near corner.
- Then the boundary steps inward (a notch cut from the bottom-left corner of the overall 437×891 bounding box): kitchen wall 260cm (left, at the stepped-in depth), then 180cm perpendicular (stepping back out towards the bottom wall), then bottom wall 177cm back to the bottom-right corner.
- Check: 177 + 260 = 437 — the notch exactly accounts for the rest of the overall width, confirming the reading.

So the footprint is an L-shape / rectangle-with-a-corner-notch: overall bounding box 437cm × 891cm, with a 260cm × 180cm rectangular notch removed from the corner where the kitchen and entrance meet. **Confirmed: the notch is the bathroom** — i.e. that 260×180cm corner of the overall bounding box belongs to the bathroom, not the living room/kitchen floor.

**Derived polygon** (metres, going A→B→C→D→E→F→A; +X = overall width direction, +Z = overall depth direction, origin arbitrary — placed at the top-right corner B for convenience):
- A (top-left) = (-4.37, 0)
- B (top-right) = (0, 0)
- C (bottom-right) = (0, -8.91)
- D = (-1.77, -8.91) — bottom wall is 1.77m (C→D)
- E = (-1.77, -7.11) — the 1.80m notch wall (D→E)
- F (left wall bottom) = (-4.37, -7.11) — the kitchen wall, 2.60m (E→F)
- back to A: left wall F→A is 7.11m

Right wall (B→C, 8.91m) carries the doorway/cupboard/freezer/cupboard/sofa run. Wall E→F (2.60m) is the same length as the kitchen's previously-recorded "front wall run" — likely the same wall. Wall D→E (1.80m) is the same length as the previously-recorded "doorway gap" — likely also the same wall, but as an actual notch wall (bathroom wall) rather than open clear space as originally assumed. **Still needs reconciling**: the existing kitchen unit placements (left wall run 3.62m, tall larder, peninsula 3.5m/corrected to 360cm low cupboard run, cupboard/freezer/cupboard — now understood to be the 84/103/84 units on the 8.91m wall, not a separate tower) all need re-anchoring to this new polygon before the 3D model is rebuilt.

## Kitchen layout — simplified (2026-10-24, fifth pass, supersedes earlier kitchen readings)

Earlier kitchen sketches proved too ambiguous to place reliably (see "Kitchen units" section above — left run 3.62m, peninsula 3.5m/360cm, 82cm gap, cupboard/freezer/cupboard etc. were all best-effort reads). George has simplified instead of trying to resolve every number:

- Worktop runs in a **U shape**: two legs + a base.
- **Both legs of the U = 260cm long.**
- **All worktop is 60cm deep** (both legs and the base).
- **Base of the U (containing the sink) = 130cm long.**
- Sink sits in the base of the U. A hob was shown in the discarded sketch on what looked like a separate/lower section — not yet re-confirmed against this simplified U; treat hob position as unplaced for now.
- This supersedes the earlier "left wall run 3.62m / front run 2.6m / peninsula 3.5m or 360cm / 82cm gap / cupboard-freezer-cupboard tower" description — the U's two legs replace the left run and peninsula, and the base replaces the old front run.
- **Orientation (2026-10-24, sixth pass)**: the U's open side faces across the room toward the doorway-side cupboard/freezer/cupboard run (the 84/103/84cm units on the long 891cm wall) — i.e. the U looks out across the open floor at that run.
- **Left wall placement (2026-10-24, sixth pass)**: a single long low cupboard, 360cm, runs along the room's **left wall** (A→F, 7.11m — this is the wall previously miscast as a "peninsula" or "tower"; it is one continuous run, not three separate units). Sequence down the left wall from the top-left corner (A): 79cm gap, then the 360cm cupboard, then an 82cm gap, then the kitchen U begins.
- **Confirmed (2026-10-24, seventh pass)**: the U's 130cm base sits flush against the same left wall, continuing straight on after the 82cm gap, with the two 260cm legs projecting perpendicular into the room. Still unplaced: the tall larder/fridge unit (45cm) and the hob.

## Sofa + bookcase positioning (2026-10-24, seventh pass)

- **Sofa confirmed on the right wall** (B→C, 891cm) — same wall as the doorway/cupboard/freezer/cupboard run already modelled. This matches the existing 300cm L-shaped sofa (main piece 210×108, chaise 195×90) already placed against that wall — no change needed there.
- **Confirmed: bookcase** — 120cm wide (along the top wall) × 35cm deep, positioned at right angles to the sofa in the **upper corner** of the room (top-right corner, where the right wall meets the top wall, i.e. runs along the top wall B→A direction). A 25cm gap separates the bookcase from the start of the sofa run.
- **3D model note**: the bookcase was placed flush against the top wall (more physically plausible than floating it off the wall by a gap). With the sofa's position anchored from the doorway/cupboard side (well-confirmed, see sum above), this leaves a computed ~15cm gap to the sofa rather than the stated 25cm — a ~10cm discrepancy, within hand-measurement tolerance given the 891cm wall itself summed to 901cm using all the individual pieces including this gap. Not treated as an error requiring rework.
- Sketch also shows extra sofa step detail (108 / 20 / 90 / 195 near the top of the sofa run) beyond the already-modelled two-box L-shape — **not yet clear whether this refines the existing shape or is redundant with it**; treating the existing simplified two-box sofa as good enough for now unless told otherwise.

## Floor and wall finishes (from photos, 2026-10-25)

- **Floor**: pale grey-beige oak-effect plank flooring, 19cm plank width (measured from photo). Modelled as a procedural canvas texture (`makeFloorTexture()` in `index.html`) tiled at the real 19cm width; plank length (1.2m) is an ASSUMPTION, not measured — only affects where the drawn end-joint seams repeat, not the overall look.
- **Walls**: light warm greige paint, flat/matte.
- **Kitchen units**: white gloss.
- **Fridge/freezer**: Samsung stainless-steel American-style (side-by-side, water/ice dispenser) — modelled as a brushed-steel material on the existing placeholder box, not a new shape.
- **Sofa**: white/cream leather L-shaped corner sofa with chaise, grey trellis-pattern and black/white patterned scatter cushions (cushions not modelled, colour of the sofa body only).
- **Bookcase**: plain white (previously a placeholder wood-brown colour, `tableMat` renamed `bookcaseMat`).
- **Sideboard/TV unit**: this is the existing 360cm low cupboard already modelled along the left wall (`kitchenGroup`, `cupboardStartZ`/`cupboardEndZ` in `index.html`) — not a separate piece. It already uses `unitMat` (white gloss), so no further change needed.
- **Explicitly decided against (2026-10-25)**: glass dining table + black chairs, red accent "Cone"-style chair — not to be added.
- Not modelled, not yet decided either way: round mosaic mirror, gallery wall art (minor wall decoration).

## Kitchen units, worktop, sink, hob, oven, microwave (2026-10-25)

No photo shows the worktop or these four appliances specifically (only the fridge/freezer was photographed), so all of this section is geometry/placement built to look plausible rather than measured or photo-matched — flagged as ASSUMPTION in the `index.html` comments at each spot.

- **Worktop cap**: every worktop-height cabinet run (left-wall cupboard, both kitchen-U legs, the base unit, the front-wall run, and the two doorway-side cupboards — not the fridge/freezer, which is taller and standalone) now has a thin stone-effect laminate cap (`worktopMat`, `addWorktopCap()`) with a small overhanging lip, instead of the units reading as flat-topped boxes.
- **Sink**: a stainless basin + chrome mixer tap (`makeSink()`), inset into the worktop cap of the base unit — the unit already annotated in the code as "containing the sink". Tap mounted at the wall-side back of the basin.
- **Hob**: a four-ring dark-glass hob (`makeHob()`), ASSUMPTION placement roughly a third of the way along the kitchen-U's first leg (`leg1`).
- **Oven**: built under the worktop directly below the hob (`makeOven()`), set into the same leg, door facing into the walkway inside the U — a believable hob-over-oven "range" pairing, not a measured one.
- **Microwave**: a white-gloss countertop microwave (`makeMicrowave()`, matches `unitMat`), placed on the front-wall-run worktop near the open end of the U.
- New shared materials: `worktopMat` (worktop cap), `hobMat` (hob glass / oven window / microwave door), `chromeMat` (tap, hob rings, handles).

**Corrections, same day, second pass** — George flagged the first version as not reading as his actual kitchen at all: no cupboard doors visible under the worktops, the oven on the wrong leg, and the sink effectively invisible against the worktop.
- **Cabinet doors added** (`addCabinetDetail()`): every worktop-height cabinet run now gets a dark recessed kickboard along the floor, vertical door-seam grooves spaced ~45cm apart, and a chrome handle per door — so the units read as a run of individual cabinet doors, not a plain slab. Applied to all worktop-height runs except the hob/oven leg (its front face is mostly taken up by the hob/oven themselves, so cabinet-door detail there would visually collide with them).
- **Hob/oven moved**: previously both were on leg1 (the sink's own leg) — a bad floor plan (sink and hob crowded onto the same run) and the oven only had ~8cm of worktop left before the wall corner. Moved to the other leg (the E-F front-wall run), oven door facing into the walkway as before. Re-verified via screenshots that the oven door/window/handle and the hob rings render on the correct (room-facing) face, not the wall-backed one.
- **Sink made visible**: added a raised chrome rim around the basin, and gave the basin interior its own much-darker material (`sinkBasinMat`, near-black) instead of reusing the mid-grey `applianceMat` — the basin was barely distinguishable from the worktop/fridge colour before. Confirmed via a top-down screenshot that the basin now reads clearly as a sink void, not a shadow.

## Plan
1. Living room in full detail: furniture and finishes, first loop routed clear of furniture, both views.
2. Room builder and track builder (OO-gauge pieces, points, gradients, tunnels through walls).
3. Sign-in, saving and a gallery of public layouts (Supabase), deployed on Netlify from GitHub.
4. Extend the track through the rest of the flat.

## Feature roadmap (2026-10-25)

Ten further ideas were discussed and assessed for feasibility. The core architectural fact driving the sequencing: everything today assumes **one closed track loop** (a single `curve` + shared arc-length table, see `pointAndTangentAtDistance()` in `index.html`) and **one train** (`trainDist`, hard-coded `loco`/`coach1`/`coach2`). Several ideas fit inside that model as-is; others (points, signals, sidings, bridges, branching) need that replaced with a **track graph** (nodes/edges, junction choices) — the one genuine architecture rewrite in this list. Sequencing avoids doing that rewrite twice.

**Phase A — visual/polish (no architecture changes, independent of each other, can start any time):**
- Realistic walls/floor/furniture finishes, from photos (settee should look like a settee, not a blob) — textures + more detailed furniture geometry, same technique already used for the loco/coach rebuild.
- More realistic train/carriage models (push further than the current boiler/cab/chimney build).
- Scenery: trees, lakes, rivers etc. — more decorative meshes.
- Train sound — Web Audio API, loop pitch/volume tied to speed; must start on first user click (browser autoplay restriction).
- **Engine driver view** — a third camera mode, rigid (not orbiting) to the loco's own position/heading, mounted in the cab, facing forward along the same tangent `placeAt()` already computes. Needs the loco's own body hidden/culled while this camera is active (no interior modelled — camera would see inside faces of the boiler/cab otherwise). Wider FOV (~75-80°) than the chase cam's 60° so the tight OO-gauge curves read well through the "windscreen". Build it to follow "whichever train is selected", not hard-coded to `loco`, so it doesn't need rework once multi-train (Phase B) lands. Mouse-look and speed-tied bob/sway are nice-to-have v2 polish, not needed for v1.

**Phase B — multi-train (generalise `trainDist` into a list of trains, still one loop, no graph needed):**
- More than one train on the circuit, each with its own speed and type (e.g. steam vs electric — different models, pairs naturally with the train-realism polish above).
- Catch-up behaviour: a following train caps its speed to maintain a minimum gap to whichever train is ahead of it on the same loop.
- Basic stations/schedules: named stop-points along the loop, pause-for-N-seconds logic — works fine on a single loop, no routing decisions needed yet.

**Phase C — track graph rework (the big pivot; everything below depends on this):**
- Points, signals, a second track, bridges (mostly visual), gradients (track going up/down isn't supported at all yet). Track becomes nodes + edges; trains choose a route at junctions instead of following one fixed loop.

**Phase D — built on the graph (after Phase C):**
- Overtake siding: a side route a faster train can use to pass a slower one.
- Full scheduling: different trains stopping at different named stations, not just pause-points on one loop.
- Tunnels through furniture (cupboards, under the bed etc.) — visual treatment + routing, same bucket as the hall/bedroom extension below.

**Phase E — flat expansion:**
- Extend track into the hall and both bedrooms. Partly blocked: bedroom sizes aren't measured yet (hall width 1.4m and ceiling height 2.28m are already in NOTES.md, bedroom dimensions still needed). Can be done as a simple loop extension (no graph required) if it stays one line, or combined with Phase C if a junction is wanted where the hall meets the living room.

## Real scan view (2026-10-26)

George felt the hand-built room/furniture still didn't read as recognisably "his flat" to a child, even after the kitchen detailing pass. Rather than chase photo-textured boxes further, tested true photoreal capture: George scanned the whole flat with Polycam ("3D Space" mode) and exported GLTF/GLB (`lounge-scan.glb`, ~24MB, captures the whole flat not just the lounge).

- Added a third **"Real scan view"** button/camera mode in `index.html`, alongside Child's-eye and Bird's-eye.
- The scan is rendered in its **own `THREE.Scene`** (`scanScene`), not merged into the hand-built room — the scan's own geometry already contains a full room/furniture at a scale and origin with no known relationship to the hand-built coordinate system, so overlaying both would just produce two conflicting, misaligned rooms. `animate()` picks which scene to render based on which camera is active.
- Scan is **lazy-loaded** on first click of the button (24MB — no reason to pay that cost on every page load), with a status line (`#scanStatus`) showing load progress.
- Scan materials are swapped to unlit `MeshBasicMaterial` (texture map only, no relighting) — the captured textures are already baked/lit from the scan itself, and rendering them through normal `MeshStandardMaterial` + scene lights came out almost black. This was proven out first in a standalone diagnostic viewer (`scans/test.html`, loads `../lounge-scan.glb`) before being carried into the real app.
- Camera auto-frames from the loaded model's bounding box (center + max dimension), since the scan's real-world framing isn't known in advance.
- Verified: switching to Real scan view shows a genuinely recognisable scan of the flat (sofa, bookcase, fireplace, kitchen units, wall art); switching back to Child's-eye/Bird's-eye renders the hand-built scene cleanly with no leftover state.
- Not yet done: aligning/trimming the scan to just the lounge, or using it for anything beyond a standalone "real photo" view (e.g. no plan to merge it with the train track).
