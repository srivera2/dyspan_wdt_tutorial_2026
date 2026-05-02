---
layout: page
title: Tutorial Timeline
---

In the ```Geo2SigMap``` repo, you can find the tutorial notebooks in ```\research\examples```. If you are operating locally, make sure you have switched to the ```\dyspan2026``` branch. These notebooks have been configured to work with the newest release of ```Sionna-RT``` (v2.0.0).

**The following section summarizes each of the tutorial notebooks in order:**

### Tutorial 1: Introduction to Coverage Maps
Generate a radio coverage (path gain) map using Sionna RT on a Geo2SigMap scene. Configure a transmitter at 3.65 GHz (CBRS band), run the RadioMapSolver over a grid of receiver locations with up to 5 reflection depths, and visualize the result overlaid on the 3D scene. Covers both flat-terrain and LiDAR-terrain scene variants, including area-weighted projection of path gain onto the LiDAR mesh.

### Tutorial 2: Ray Tracing and Link-Level Simulation
Perform point-to-point ray tracing between a transmitter and outdoor receivers using Sionna RT's PathSolver. Outdoor receiver positions are validated via upward ray casting, and traced paths are parsed into a structured dataset capturing path type (LOS, specular), complex gain, delay, and AoA/AoD angles. The tutorial concludes with a link-level simulation that converts the channel impulse response into a time-domain channel and evaluates symbol error rate under 256-QAM modulation.

### Tutorial 3: Visualizing Measurement Data
Visualize real-world RSRP field measurements on an interactive Bokeh map using OpenStreetMap tiles. Loads a 46,000-point CBRS dataset collected on the Duke University campus, reprojects GPS coordinates to Web Mercator, and renders signal strength with a color-mapped scatter plot. Users can interactively filter by device type and Physical Cell ID to explore spatial signal patterns.

### Tutorial 4: ML-Based Coverage Prediction
Run Geo2SigMap's two-stage U-Net pipeline and evaluate against field measurements. The first U-Net takes a 2D building height map, transmitter position, and a 3GPP UMa path loss baseline as input to predict an isotropic coverage map. The second U-Net refines this with 200 sparse RSRP samples — either real measurements or Sionna RT-simulated — and outputs a 128×128 directional coverage map at 4 m/pixel resolution, scored against ground truth using RMSE and MAE.

### Tutorial 5: 28 GHz Urban mmWave Analysis
Analyze 28.5 GHz mmWave propagation in downtown Boulder, Colorado using the public NIST measurement dataset. MATLAB header and MPC files are parsed to extract TX/RX GPS coordinates, multipath delays, AoA angles, and per-sector path gains. A 512×512 m Sionna RT scene is built from OSM data with ITU-R brick/concrete/metal materials, ray tracing is run at max depth 3, and simulated path gains are compared sector-by-sector against measured MPC data with separate RMSE evaluation for indoor and outdoor receivers.