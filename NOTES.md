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
4. Extend the track through the rest of the flat. **Hall done (2026-10-26) — see "Hall: real scan + oval track" below.** Next: bedroom 1, then bedroom 2, same real-scan method.

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
- Superseded by "Real scan alignment" below — the scan is no longer a separate standalone view; it's now a backdrop aligned into the same coordinate space as the track/train.

## Real scan alignment (2026-10-26)

George: "if I'm going to impress my grandchildren it has to be real" — a separate, unmerged scan view wasn't enough; the train needed to visibly run through the real scanned room, not a hand-built box.

- Derived a rigid transform from the scan's local coordinate space into `ROOM_POLY` space (the hand-built room/track's coordinate system) by raycasting known landmarks in the scan and comparing against ROOM_POLY's known wall lengths:
  - Cast straight down (`THREE.Raycaster`, origin above, direction `(0,-1,0)`) at a grid of `(x, z)` points to find exact floor/wall boundaries — far more reliable than raycasting through a top-down perspective camera, where even near-vertical rays are measurably off-axis near the frame edges and give inconsistent results.
  - Found the long kitchen wall as a very consistent floor-to-wall transition at scan-local x ≈ 2.95–3.0, flat across a 5m run in z — matched against `ROOM_POLY`'s west wall (hand x = -2.185).
  - Found the room's long clean floor run in z spans scan-local z ≈ 0.4–7.5, matching `ROOM_POLY`'s long wall length (7.11m) closely.
  - The two walls being X-constant in both frames with sign-flipped X at first suggested a plain 180° rotation, but that produced an impossible out-of-room result for one wall's far end on cross-check — the real relationship is a **mirror on X only** (Z unchanged), likely from a handedness/winding difference between `ROOM_POLY`'s arbitrary corner-walking direction and Polycam's own export axes.
  - Confirmed the fit visually: drew the `ROOM_POLY` outline as a wireframe overlay directly into the scan (temporary debug code, since removed) and screenshotted from a top-down scan camera — the overlay traced the real walls closely once the mirror + translation was right.
  - Final transform: `scanX = -handX + 0.79`, `scanZ = handZ + 4.83` (`SCAN_TX`/`SCAN_TZ` in `index.html`).
- Restructured `index.html`: the hand-built floor/walls/kitchen/furniture now live in `handBuiltRoomGroup`; the scan model loads into `scanRoomGroup` (added directly to the main `scene`, not a separate one), positioned with `scanRoomGroup.scale.set(-1,1,1)` + `position.set(SCAN_TX, 0, -SCAN_TZ)` to apply the inverse of the derived transform. Track/train stay outside both groups, in `scene` directly, so they're always visible regardless of which backdrop is showing.
- The separate `scanCamera`/`scanScene`/`scanControls` are gone. "Real scan view" is now a **backdrop toggle** (button relabels to "Hand-built room" when active) that swaps `handBuiltRoomGroup.visible` / `scanRoomGroup.visible` and works from whichever camera (Child's-eye or Bird's-eye) is already active, rather than switching to its own dedicated camera.
- Verified in both camera modes: Bird's-eye view clearly shows the track loop running through the real floor, past the real sofa; Child's-eye (chase cam) renders the scan close-up, though the scan has natural coverage gaps right at floor level in places (a handheld-Polycam-capture artifact — the scanner's own position tends to leave a gap underfoot — not an alignment bug).
- Alignment is informally calibrated (raycast landmarks + visual fit), not pixel-exact — acceptable for this use, and the better option given the lounge's genuinely irregular (non-rectangular, notched) real shape.

### Fix: mirror → proper rotation, floor offset (2026-10-26, same day)

George, after testing the above: "there is lots of distortion... the track is floating and it goes through walls... not matched to the furniture," then "the view I'm seeing is flipped. The sofa is on the lh wall."

Root cause: the transform above (`scale.x=-1`, Z unchanged) is a **single-axis mirror** (determinant -1, a true reflection), not a rotation. Wall-length/floor-extent landmark matching can't tell a mirror from a rotation apart — both preserve distances — so the earlier fit "looked right" on the wireframe overlay but was the wrong one of the two candidates. Consequences:
- Every real, photographic texture in the scan was mirrored, so the room read as backwards to someone who actually lives there (sofa apparently on the wrong wall) — a reflection flips handedness, which a real captured room can never actually have relative to itself.
- It also matched the WRONG real-world points to each hand-built `(x,z)`, which is what caused the floating/wall-clipping/furniture-mismatch: the floor-height correction (`SCAN_FLOOR_Y`) looked necessary at ~0.39m, but dense raycasting showed the real floor was still averaging ~0.37m off even after that — not a residual tilt, but a symptom of sampling the wrong part of the room entirely.

Fix: use a proper 180° rotation about Y instead — `scale.set(-1,1,-1)` (both X and Z negated, determinant +1), with `position.set(SCAN_TX, -SCAN_FLOOR_Y, SCAN_TZ)` (Z translation sign flipped to match). Verified by:
- Drawing the `ROOM_POLY` wireframe + coloured corner markers (A–F) directly in world space and screenshotting bird's-eye: under the old mirror, the room's notch (the kitchen cutout corner of `ROOM_POLY`) landed over an unrelated dark area; under the corrected rotation, the notch lands cleanly over the real kitchen cabinets/sink in the scan — the semantically correct match.
- Re-running the dense floor-height raycast grid (425 points) under the corrected transform with the *same* `SCAN_FLOOR_Y` offset: mean +0.01m, median +0.02m from world y=0 (vs. -0.37m average miscalibration before) — confirming the float/clip bug was the chirality bug, not a separate vertical calibration problem. Nudged `SCAN_FLOOR_Y` from -0.39 to -0.37 to re-centre on the new median.
- Child's-eye screenshots of the train on the real floor near a wall: wheels sit on the floor, no clipping, plausible wall clearance.

## Lounge scan abandoned for active track work; hall built from a fresh scan instead (2026-10-26)

A later pass tried to extend the dual-lane loop through the kitchen using raycast-derived furniture positions read from `lounge-scan.glb`, and got a kitchen footprint that contradicted the confirmed real layout ("you say the kitchen stretches across the room but that is incorrect... the original layout we had was correct even if I decided to skip the table and the red chair"). Diagnosis, not a rotation/alignment bug (that was already fixed above and re-verified): the lounge scan has **severe SLAM drift baked into the mesh itself**, not just a bad raycast reading.

- Bounding-box sanity check: the lounge scan's own `THREE.Box3` is 9.06m × 5.42m × 19.3m — more than double the real room (4.37m × 8.91m, ceiling 2.28m) in every dimension.
- Critically, this isn't one bad outlier chunk: **every individual mesh chunk** (mesh_0 through mesh_9+) independently comes back similarly oversized (~7-9m × ~16-19m each) — the signature of drift accumulating with distance from wherever the scan was anchored, not a single corrupted piece that could be deleted.
- Conclusion: trust the hand-measured layout over this scan's raycast geometry for anything beyond the near-the-anchor area already visually verified (sofa/notch region). The scan stays as a visual backdrop only; no further clipping-fix work planned against it for now.
- This does **not** mean abandoning real scans generally — George: "no. I still want to aim for reality rather than sketches." The fix was a better capture, not a different method: "scan the hall with all doors closed, scanning the full volume... We can then fit a simple oval track in it."

## Hall: real scan + oval track (2026-10-26)

First room built entirely from a real scan rather than hand measurement + sketch (the living room's method) — chosen deliberately as the simplest next room (per George: "abandon the lounge/kitchen for now and try building a track in a simpler room, such as the hall, then add on a bedroom, then another bedroom etc").

- **Capture**: George scanned the hall with all doors closed (full volume, doors-closed → reads as a simple rectangle). Saved as `scans/hall-scan.glb` (4.08MB).
- **Scan-quality check** (same bounding-box method used to diagnose the lounge, run first before trusting anything derived from it): bounding box 1.79 × 3.26 × 5.12m vs tape measurements 1.4 (width) × 2.28 (ceiling) × 4.38m (length) — only mildly oversized (~8-43%), and just 2 large, consistently-sized mesh chunks + 1 tiny one (a small object), not the lounge's 10 wildly-inconsistent chunks. Clean, closed-loop capture.
- **Which measurement to trust**: scan's footprint (1.50 × 4.78m) is 7-9% bigger than the tape measurement (1.4 × 4.38m). George: "I gus the scan is reading into door recesses etc, so use the scan" — the scan's own measured envelope is the real usable volume including door reveals, the tape measurement was a simpler point-to-point read. **Scan dimensions are now the trusted ones.**
- **Alignment** (PCA, not hand-picked landmarks — more robust for a simple rectangular room than the lounge's visual wireframe-overlay method): floor-height histogram (2cm bins) found the dominant floor cluster cleanly at y≈-1.57 to -1.56. Floor-point `(x,z)` cloud → mean/covariance → principal axis angle. Final constants (`index.html`, `scanHallGroup`):
  - `HALL_FLOOR_Y = -1.57`
  - `HALL_CENTER = { x: -0.07255600814664044, z: 0.012245417515271695 }`
  - `HALL_ANGLE = -1.5446548533802604` (radians)
  - Fitted rectangle from the same pass: long axis ≈ 4.76–4.78m, short axis ≈ 1.50–1.51m (`HALL_BOUND_W`/`HALL_BOUND_D`).
  - Applied as `scanHallGroup.rotation.y = HALL_ANGLE`, `scanHallGroup.position = R_y(HALL_ANGLE) · (-HALL_CENTER.x, -HALL_FLOOR_Y, -HALL_CENTER.z)` — three.js's `rotation.y` convention matches the PCA (u,v) projection formula exactly, so world x/z after this transform ARE the PCA long/short axes directly; no separate axis-remapping needed.
- **Usable width profile**: sweeping along the long axis and raycasting outward from centre found a stable ~1.28–1.38m-wide corridor through the core/middle of the hall, with real (expected) narrowing/erratic readings only right at both ends — door reveals/thresholds, consistent with George's "reading into door recesses" explanation, not a scan defect.
- **Track**: a single simple oval (not the living room's dual-lane loop — no furniture to route around once doors are closed). Radius 0.35m, centreline at v=0.05, turn-circle centres at u=-1.0 and u=0.6 (`HALL_TURN_RADIUS`/`HALL_CENTRELINE_V`/`HALL_WEST_TURN_U`/`HALL_EAST_TURN_U` in `index.html`). Validated by sampling 301 points round the candidate curve and raycasting each straight down against the real scan mesh: **0 points off the real floor height or missing the mesh**.
- **Implementation**: refactored the single module-level `curve`/`trackPts`/`trackDist`/`trackLength`/`pointAndTangentAtDistance` into a reusable `buildTrackSystem(waypoints)` factory, instantiated once for the living room's existing loop (`livingRoomTrack`) and once for the new hall oval (`hallTrack`), selected via a module-level `activeTrack`. `loco`/`coach1`/`coach2`/couplings moved from being children of the living room's `trackGroup` to being direct `scene` children, so the same train meshes run on whichever track is active. New **"Hall"** button (`#viewHall`) swaps room+track+background+bird-frustum bounds together (mutually exclusive with the living room, including its own "Real scan view" sub-toggle, which is disabled while in hall mode) and resets `trainDist` to 0 on switch. Verified in the live preview: clean toggle both directions, train runs on the real hall floor with visible wall clearance in both Child's-eye and Bird's-eye views, no console errors.
- Not yet done: a connecting tunnel between the hall and living room loops (noted in the living room's TRACK_WAYPOINTS comment as a future target, south end near the doorway foyer) — the two rooms/tracks are currently two independent, mutually-exclusive scenes, not a connected network. Left for the track-graph rework (Phase C in the feature roadmap) if/when branching between rooms is wanted.

Lesson for any future landmark-based rigid-transform fit between two independent real-world captures: **never accept a single-axis mirror** as the fit — only translation + rotation (determinant +1) are physically valid for aligning two real, non-reflected captures of the same space. If a mirror seems to fit, a rotation that also fits is the one to trust (and if truly no rotation fits, the bug is elsewhere, e.g. in one of the two source coordinate systems itself, not in needing a reflection).

### Fix: rail/sleeper rendering gap — real floor isn't flat (2026-10-26, same day)

Reported: "a lot of the rendering of the track is missing. The train runs ok on the whole circuit." A 401-point raycast sweep straight down along the oval's own curve found the real hall floor varies from -0.011 to +0.015m around the single flat `HALL_FLOOR_Y` offset (a real bump, not a scan defect) — worse near the west/top. At the living room's default rail height (3mm, tuned for its perfectly flat hand-built floor), the rails sat *below* that bump in places and were swallowed by the real scan mesh there, even though the train's own position math (which doesn't depend on the rendered mesh) was always correct — hence "train runs fine, track looks broken." Fix: `buildTrackSystem(waypoints, trackHeight)` now takes a per-track-system height; gave the hall a 25mm rail height (since increased, see below). General lesson: any *real* (non-hand-built) scan floor needs its own measured, raised rail height — never assume a flat plane at y=0.

### Extend hall track, widen it, add a second concentric track for opposite-direction running (2026-10-26)

George: "Extend the hall and make the track wider and add a second track so we can have trains going in opposite directions."

- **Re-profiled the real hall floor** (same raycast-sweep method, denser this time: ~0.1m grid along the full long axis, ~0.05m across) to find how much of the hall was actually usable beyond the original conservative oval. Found the real floor usable from roughly u=-2.05 to u=+2.05 (narrowing quickly beyond — the two doorway-reveal ends), with a stable ~1.3–1.45m width through most of that core — except a local pinch to ~1.2m right around u=0 (almost certainly a door reveal into a side room partway along the hall, not either end).
- **New geometry** (`index.html`): `HALL_CENTRELINE_V=0.0`, turn centres at `HALL_WEST_TURN_U=-1.37`/`HALL_EAST_TURN_U=1.37` (was -1.0/0.6) — straight sections now ~2.7m each, chosen with margin against the mid-hall pinch. Two concentric ovals share these turn centres: `HALL_TURN_RADIUS=0.38` (inner, was 0.35) and `HALL_TURN_RADIUS_2=0.48` (outer, new) — both validated with 0 width-limiting bad points at these radii (the mid-hall pinch is exactly why the outer radius isn't bigger).
- **A real feature, not a bug**: a handful of raycast samples near (u≈1.7–1.8, v≈0.2) return a very high hit (~y=2.4–2.6) instead of floor height — turned out to be an open door in that part of the hall (visible in the bird's-eye screenshot as a bright rectangle), letting the ray see past the hall wall into the next room. Confirmed harmless: it's a background-mesh gap, not a floor obstruction, and doesn't affect the rendered rails/sleepers (separate geometry) at all.
- **Floor bump re-measured** for the longer/wider pair of ovals: -0.04 to +0.02m (similar magnitude to the original, slightly larger since more real floor is now covered). `HALL_TRACK_HEIGHT` raised from 0.025 to 0.03m with margin.
- **Second train**: `buildTrackSystem`/`buildTrackMeshes` reused as-is for the new outer oval (`hallTrack2`/`hallTrackGroup2`). A second loco+2 coaches (`loco2`/`coach2a`/`coach2b`, green body colour to tell it apart from the first train's blue/maroon) run permanently on `hallTrack2`, grouped under `train2Group` so visibility toggles with hall mode in one line. `placeAt()` generalised to take an explicit track system (defaulting to `activeTrack` so the first train's calls are unchanged). A new `trainDist2` **decrements** instead of incrementing — same shared `scaleMph`/`running` controls, opposite direction round its own loop, so the two trains visibly pass each other like a real double-track line.
- Verified in the live preview (bird's-eye + child's-eye): both ovals render as complete closed loops along their full new length, both trains move correctly in opposite directions, living-room round-trip unaffected.
- Still not done: the hall/living-room tunnel connection (same note as above — Phase C track-graph rework).

## Bed2: standalone loop, 3-side skirt around the bed (2026-10-26/27, corrected)

Per standing instruction, bed1/bed2 are built as their own standalone closed loops (own view button, same pattern as Hall) and explicitly **not** spliced into the hall oval yet — George wanted the hall oval demoable to his grandson first.

- **Capture**: `scans/bed2-scan-v2.glb`, same PCA profiling methodology as the hall (floor-height histogram, floor point-cloud centroid/angle).
- **First cut was wrong — caught by George live in the preview**: an east-wall-strip-only loop was built and initially believed correct (floor classifier treated raycast misses as "passable"). George reported the train "wandering around inside the wardrobe, not coming through the wall from the hall cupboard and circumnavigating the bed (3 sides) before exiting through the wall into bed 1" — confirmed by a close-up screenshot showing the track running right past visible hanging clothes. Root cause: the classifier conflated "no raycast hit" (genuine void/furniture-interior/off-mesh) with "clear floor" — both got treated as passable. This also invalidated the earlier "no full oval is possible / topologically impossible" conclusion from the same flawed heuristic.
- **Corrected floor classifier**: raycast miss = `'x'` (no data, **not** passable — the fix), hit within 0.06m of floor height = `'#'` (clear), hit outside tolerance = `'o'` (real obstacle, e.g. furniture). Re-profiled directly against the live `scanBed2Group` mesh in the actual app (via `preview_eval`, not the separate `scans/test.html` scratch harness) — much faster iteration than the previous session's approach.
- **Real topology found**: bed footprint ≈ x:[0.32,1.12] z:[-1.14,0.7] in the scan's raw/native frame (= `scanBed2Group`'s world space directly — that group has no rotation, only a vertical shift, so waypoints are plain world (x,z), no conversion helper needed). A reliable walkway runs along the east wall (x≈1.5–1.7) from the head of the bed down to its foot; a narrower, furniture-cluttered band (desk/drawers, gaps between individual legs) runs along the west side; the head of the bed (z>1.0) opens into a wide clear area leading to a small notch right at the top of the room — a doorway, best guess the hall-cupboard side (unconfirmed against the real room). The actual wardrobe is further south/east of the bed (void/no-data for x>1.1, z<-1.44) — that's what the first loop ran through. A separate, low real obstacle (ottoman/chest — confirmed solid hit, not void) blocks a direct crossing at the foot of the bed.
- **New loop**: down the west side, a short bridge across the foot (2 waypoints spanning the low ottoman/chest, not the wardrobe), up the east side, back across the open head-of-bed area near the notch — genuinely skirts 3 sides of the bed, confirmed clear of the wardrobe void in both bird's-eye and child's-eye screenshots.
- **Real floor plan received from George** (photo of the as-built electrical layout, attached mid-session — I didn't have it accessible before this and had to ask): top-left room = **Bed 2**, with a door on its southward (drawing-orientation) wall into the hall, hall cupboard adjacent; top-right room = **Bed 1**, with its own door to the hall and a separate door to an ensuite; below that: 2nd bathroom, then kitchen (now U-shaped, supersedes the drawing's layout), then the lounge (labelled "UNIT 10" on the drawing) with the settee against its left-hand wall; "UNIT 9" block to the left of the drawing is a neighbouring flat, ignore. Double (green) doors lead onto the main hallway. **Not yet mapped to the scan's own coordinate frame** — which real-world wall corresponds to which scan axis is still unconfirmed; doesn't block the standalone loop, only matters once actual wall-splicing to the hall/bed1 happens.
- Debugging detail worth remembering: raycasting via `preview_eval` against a freshly-mutated `Group` can read a stale `matrixWorld` if `updateMatrixWorld(true)` isn't called first (the page's own `requestAnimationFrame` loop isn't reliably ticking in the automated preview context).
- **Implementation**: `scanBed2Group`/`loadBed2ScanIfNeeded()` (hall pattern otherwise), `BED2_TRACK_WAYPOINTS` now plain raw (x,z) pairs (no `bed2LocalToRaw()` wrapper — removed, since these were derived directly against the live mesh), `bed2Track`/`bed2TrackGroup` via the existing `buildTrackSystem`/`buildTrackMeshes`. **"Bed 2"** button (`#viewBed2`), mutually exclusive with both the living room and the Hall. Not yet raycast-profiled for real floor unevenness the way the hall's `HALL_TRACK_HEIGHT` was (still using the flat-floor default) — revisit if the train visibly dips/clips.
- Verified in the live preview (bird's-eye + child's-eye): loop clearly skirts 3 sides of the bed, nowhere near the wardrobe/clutter area, train runs smoothly.
- Not yet started: bed1's equivalent floor-profiling/loop-building work.
- **Reverted (2026-10-27).** A same-day follow-up briefly replaced this standalone loop with a "Hall journey" — one train vanishing from the end of the hall oval and reappearing in bed1, then bed2, then back in the hall, stitching three independently-aligned scans together via a hidden swap rather than a real visible crossing. George's reaction: "This is rubbish. We are getting further and further away from my original idea... What I wanted was a model railway that would run through all the rooms in my flat... and it would look like my flat in every room" — the hidden-swap illusion and the difficulty routing round real scanned furniture clutter (bed1/bed2) were explicitly called out as not meeting the goal. **Reverted entirely** back to `index.html` as it was at commit `a582a85` (full hall twin closed ovals, no bed1/bed2 tracks, no "Bed 2" button, no journey state machine) — see "Where this leaves the whole-flat goal" below for the real path forward being considered instead.

## Where this leaves the whole-flat goal (2026-10-27)

The actual goal (George, restated): a model railway that visibly runs through every real room of the flat (hall, bed1, bed2, ensuite, bathroom, kitchen, lounge), each room looking like the real flat, with no vanishing-train tricks between rooms.

The scan-swap approach (hall/bed1/bed2 above) can't deliver that: separately-captured Polycam scans have no shared coordinate frame (confirmed earlier, see "Lounge scan abandoned..." — SLAM drift makes merging separate scans unreliable), and real scan geometry bakes furniture in as solid clutter that's hard to route a clean track through automatically. Two real options discussed, not yet decided:

1. **Hand-build every room** like the living room — real measurements + simplified placed furniture, giving one true continuous coordinate space so track can run through actual doorways between actual rooms. Slower upfront (needs dimensions/furniture layout per room from George, same process as the lounge), no vanishing-train tricks, and furniture can always be left a gap for track since it's placed on purpose.
2. **One single continuous whole-flat scan** instead of separate per-room scans — researched 2026-10-27: the lounge scan's bad drift likely wasn't an app problem (Polycam vs Scaniverse vs Matterport are all broadly comparable for this), it was a **capture-technique** problem — loop closure should be on, and doorways/hallways need thorough, lingering overlap coverage to "glue" rooms together; scanning rooms in separate sessions (as hall/bed1/bed2 were) throws away any chance of a shared frame regardless of app. A retry as one single walkthrough scan (doors open, pause at each threshold, path ends back near the start to close the loop) might hold together where the lounge attempt didn't — not yet tried.

Not yet decided which of these two to pursue. `scans/bed1-scan.glb` and `scans/bed2-scan-v2.glb` are still in the repo (committed) even though nothing currently loads them — harmless leftovers, not cleaned up, in case the standalone-loop or journey approach is revisited.
