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
- Living room furniture: what is there and roughly where (sizes help).
- Photos of the living room from different corners, plus close-ups of the floor, a wall and a door.
- Supabase project URL and anon (public) key. Never the service_role key.
- Name of an empty GitHub repository for the code.

## Plan
1. Living room in full detail: furniture and finishes, first loop routed clear of furniture, both views.
2. Room builder and track builder (OO-gauge pieces, points, gradients, tunnels through walls).
3. Sign-in, saving and a gallery of public layouts (Supabase), deployed on Netlify from GitHub.
4. Extend the track through the rest of the flat.
