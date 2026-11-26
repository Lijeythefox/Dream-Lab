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

- **Ground floor:** the living room, music wall, jukebox, LEGO shelf, kitchen, dining and games corner, with a front hall and floating oak stairs.
- **Upstairs:** both bedrooms, the bathroom, battlestations, the drinks fridge, the fireside chat corner and a long glass balcony.
- **Outside:** a pool with a sunken deck island, an outdoor lounge, the skatepark on the lawn and a garden, all in a clearing surrounded by forest.
- **Basement lab:** everything from the warehouse floor, including the fab shop, PCB line, studio, arena, gym, sauna and bouldering wall. To get there, walk into the glass "THE LAB ↓" pavilion in the garden and press `E`.
- **Cars:** a carport by the top of the driveway with a white 911, a blue Mustang and a ute, plus the underground garage at the bottom of the driveway ramp with the orange 911 and the black Boss 429.

Both versions have a lab cat that wanders, sits and naps, neon signs, and day/night lighting. The movie posters, arcade game names, artwork and skate deck designs are original, made for this model.

## Editing it

Everything for each version is in its own HTML file. The scene is built in plain JavaScript using small helper functions:

- `B` makes boxes, `Cy` cylinders and `Sp` spheres.
- `O` makes a group at a given x/z position.
- `col` and `fp` add walls you can't walk through.
- `label` adds a floating name tag.

Quick-travel spots are in the `SPOTS` list, and minimap zones are in `ZN`. In `house.html`, the `relocate()` function moves the warehouse contents into the house, basement and garden. After editing, open the file in a browser to check it.
