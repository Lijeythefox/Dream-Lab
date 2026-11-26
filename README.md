# Dream Lab

Two 3D walk-around versions of the same dream robotics lab and living space. Each is a single self-contained HTML file built with [three.js](https://threejs.org/) r128, which loads from the cdnjs CDN.

| Version | File | Live page |
|---|---|---|
| **Warehouse:** a 60 × 36 m warehouse with the lab on the main floor, a loft living area, and a rooftop deck | `index.html` | https://lijeythefox.github.io/Dream-Lab/ |
| **House:** a modern two-storey house in a forest clearing with a pool, and the whole lab in a basement underneath | `house.html` | https://lijeythefox.github.io/Dream-Lab/house.html |

Each page has a **Switch** button (top left, or press `H`) that jumps to the other version.

## Turning on the live page (one time)

1. Open https://github.com/Lijeythefox/Dream-Lab/settings/pages
2. Under **Build and deployment**, set **Source** to **Deploy from a branch**.
3. Set **Branch** to **main** and the folder to **/ (root)**, then click **Save**.

After a minute or two, the links above will work.

## Running it on your own computer

Download `index.html` and `house.html` into the same folder, then double-click either one to open it in Chrome, Edge or Firefox. It needs an internet connection the first time, so it can load three.js. The Switch button only works if both files are in the same folder.

## Controls

| Action | Keyboard / mouse | Touch |
|---|---|---|
| Look around | Click the view, then move the mouse | Drag on the view |
| Walk | `W` `A` `S` `D` or the arrow keys | Joystick, bottom left |
| Run | Hold `Shift` | — |
| Use stairs, slide or other actions | `E`, or the button that appears | The button that appears |
| Turn labels on or off | `L`, or the **Labels** button | **Labels** button |
| Day / night | `N`, or the **Night mode** button | **Night mode** button |
| Switch warehouse ↔ house | `H`, or the **Switch** button | **Switch** button |
| Free the mouse | `Esc` | — |
| Jump to an area | The quick-travel buttons along the bottom | Same |

## What's in the warehouse (`index.html`)

- **Ground floor:** electronics and assembly benches, a debugging area, a parts library, a skatepark, a fab shop, a PCB line, a server room, a recording studio, a film stage, a netted robot test arena, a car display bay, a gym with a cedar sauna, a bouldering wall and a downstairs bathroom.
- **Loft:** bedrooms, a bathroom, battlestations, a fireside chat corner, a lounge with a TV, LEGO shelf, jukebox and CD wall, a kitchen and dining area, a drinks and snack fridge, and a games corner with arcade machines, pinball, foosball and a slide down to the ground floor.
- **Rooftop:** reached by the spiral stairs at the kitchen end of the loft. It has a deck with outdoor sofas, a fire table, string lights, a BBQ and a telescope, plus a solar array.

## What's in the house (`house.html`)

The house is long from front to back (50 m), in a mid-poly style. A gallery hallway runs the full length on both floors so there is wall space for art, and each room has its own door instead of everything being one open space. The back of the house was pushed out: every main room is a bit deeper, and a strip of new back rooms runs behind them, each reached through a door in the old back wall.

- **Ground floor (front to back):** the front door, then the atrium, home gym, sim racing room, games room, kitchen and dining, and the living room at the far end.
- **Ground floor back rooms:** a workshop with a tool wall, a sauna and cold plunge, a mudroom for bikes and boards, a board game room, a pantry and laundry, and a library and record room.
- **Atrium:** spiral stairs and an indoor climbing wall, both going up to the second floor. Stand at the bottom of either and press `E`.
- **Upstairs:** your bedroom, battlestations, the fireside chat corner, a drinks nook, the bathroom, a friend's bedroom and a home cinema. A long glass balcony runs down the side.
- **Upstairs back rooms:** your mini lab (PC, soldering station, Bambu A1 3D printer, pegboard), a streaming booth, a plant and reading loft, the friend's ensuite and laundry, and a music practice room.
- **Dumbwaiter:** built into a column against your bedroom's back wall, running straight down to the basement lab. Stand at either hatch and press `E` to send it up or down.
- **Basement lab:** the warehouse floor, with a new layout. The recording studio is where the bouldering wall used to be, there is a dumbwaiter staging bay, and a robot test track sits where the gym was. To get there, walk into the glass "THE LAB ↓" pavilion in the garden and press `E`.
- **Outside:** a pool and deck, a garden, and a bigger skatepark (halfpipe, quarter pipe, funbox, ledge, rail). Every ramp and wall has its own graffiti, so the patterns don't repeat.
- **Cars (modelled in Blender):** the carport has a white 911, a blue Mustang and an old red Chevy C10 truck. The underground garage has a red Hellcat and a red 80s Ferrari with pop-up headlights.

**Performance:** only the 8 lamps nearest to you are real lights at any moment, the floor you aren't on is hidden (the basement when you're upstairs, and the other way round), small round parts use fewer polygons, and identical materials are merged so the scene needs fewer draw calls.

Both versions have a lab cat that wanders, sits and naps, neon signs, and day/night lighting. The movie posters, arcade game names, artwork and skate deck designs are original, made for this model.

## Editing it

Everything for each version is in its own HTML file. The scene is built in plain JavaScript using small helper functions:

- `B` makes boxes, `Cy` cylinders and `Sp` spheres.
- `O` makes a group at a given x/z position.
- `col` and `fp` add walls you can't walk through.
- `label` adds a floating name tag.

Quick-travel spots are in the `SPOTS` list, and minimap zones are in `ZN`. In `house.html`, the `relocate()` function moves the warehouse contents into the house, basement and garden. After editing, open the file in a browser to check it.
