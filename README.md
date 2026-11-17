# The Lake Floor under Northwest Ohio

An interactive 3D terrain study by **Black Swamp Analytics**.

Northwest Ohio is the bed of glacial lakes that drained away about 14,000 to 12,000 years ago. Their old shorelines survive as sand beach ridges only a few meters high, and the flat lake bed between them became the Great Black Swamp. This page rebuilds the landscape from real elevation data and lets you refill those lakes.

**[Open the live page](index.html)**. It is a single HTML file with no build step.

## Features

- **Refill the glacial lakes.** Set the water level directly, pick a lake stage (Maumee, Whittlesey, Warren, Lundy, the Black Swamp, or Lake Erie today), or play the whole sequence.
- **Live flooding analysis.** Land flooded beyond today's Lake Erie, shown in km², as a share of the land in view, and in multiples of Fulton County.
- **"How flat is it?"** A chart of land area by elevation. Click it to set the water to that elevation.
- **Local relief model.** Each cell's height minus the average height within about 1 km. It brings out beach ridges and stream cuts that a normal color ramp hides.
- **Controls** for vertical exaggeration and sun angle. A low sun reveals subtle ridges.

## Data and method

- Elevation comes from [AWS Terrain Tiles](https://registry.opendata.aws/terrain-tiles/) (Mapzen terrarium encoding, zoom 10, about 115 m per pixel), derived mainly from USGS 3DEP. The tiles are fetched and decoded in the browser.
- Rendering uses [three.js](https://threejs.org/) with custom shaders: hypsometric tint, normals from the elevation texture, 5 m contours, and water with depth tint and reflections.
- Flooded area is computed per pixel, with each row corrected for latitude in the Web Mercator projection.
- Lake-stage elevations and ages are approximate textbook values. The real shorelines tilt upward to the northeast because the land rose after the ice melted (isostatic rebound).

## Run locally

Open `index.html` through any static server, for example `python -m http.server`, then visit http://localhost:8000.

---
© Black Swamp Analytics
