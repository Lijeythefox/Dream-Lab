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

The house is square (about 26 x 26 m, two floors) in a mid-poly style. Two wings of rooms face each other across a 4 m wide gallery hallway that runs from the front door to a glass door onto the pool deck. Each wing has a strip of back rooms behind it.

- **Entry hall:** you come in through a double-height glass entry with an oak pivot door, a pendant light cluster and a sculpture. It opens straight onto the atrium (spiral stairs and climbing wall) and the open-plan living room and kitchen, and you can see the upstairs walkway above you.
- **Ground floor:** atrium, home gym, a chill lounge (TV, beanbags, bookshelf), the games room (arcade machines, foosball and the racing sim rig), kitchen and dining, and the living room, which is open to the hallway.
- **Ground floor back rooms:** workshop, a gym annex (punching bag, stretch mats, kettlebells, water cooler), mudroom, board game room, pantry and laundry, library and record room.
- **Upstairs:** your bedroom (with the dumbwaiter hatch in the wall), battlestations and fireside corner, drinks nook, bathroom, a friend's bedroom (wardrobe, desk, bookcase) and a home cinema.
- **Upstairs back rooms:** your mini lab, a streaming booth, a plant and reading loft, the friend's ensuite and laundry, and a music practice room.
- **Front garden (out the front door):** a stone path between topiary and lavender, and a round garden room with a fountain and benches. There is also a Japanese garden with a koi pond, red bridge, maples, bamboo and stone lanterns. Further in are a wisteria pergola, flower borders, tree ferns, hydrangeas and waratahs, with snow gums along the hedge.
- **Basketball court:** a full-size court out the front, with two hoops, lights and a bench.
- **Dumbwaiter, basement lab, pool, skatepark and cars:** as before. Stand at a hatch and press `E` to use the dumbwaiter; walk into the glass "THE LAB ↓" pavilion and press `E` to go down.

**Getting around:** every piece of furniture inside the house has a collider, so you can't walk through anything. Doorways are kept clear, and upstairs doors are 1.2 m wide.

**Lived-in look:** patterned rugs in most rooms (Persian, kilim, geometric, round, striped, cowhide), throws and cushions, books, plants, lamps, shoes, coat stand, photo frames, clocks and string lights.

**Performance:** only the 8 lamps nearest to you are real lights at any moment, the floor you aren't on is hidden (the basement when you're upstairs, and the other way round), small round parts use fewer polygons, and identical materials are merged so the scene needs fewer draw calls.

Both versions have a lab cat that wanders, sits and naps, neon signs, and day/night lighting. The movie posters, arcade game names, artwork and skate deck designs are original, made for this model.

## Editing it

Everything for each version is in its own HTML file. The scene is built in plain JavaScript using small helper functions:

- `B` makes boxes, `Cy` cylinders and `Sp` spheres.
- `O` makes a group at a given x/z position.
- `col` and `fp` add walls you can't walk through.
- `label` adds a floating name tag.

Quick-travel spots are in the `SPOTS` list, and minimap zones are in `ZN`. In `house.html`, the `relocate()` function moves the warehouse contents into the house, basement and garden. After editing, open the file in a browser to check it.
