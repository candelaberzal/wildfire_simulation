Wildfire Simulation Dashboard
Interactive wildfire spread simulation built in Python using stochastic spatial SIR-inspired dynamics, satellite-derived terrain data, and an interactive Dash dashboard.

This project was developed as part of a mathematical modeling project at IE University.

Project Overview
The model simulates wildfire propagation on a spatial lattice where each cell represents a portion of terrain with different vegetation density and flammability.

The simulation combines:

Spatial stochastic dynamics
SIR-inspired wildfire spread modeling
Satellite-derived terrain information
Wind-driven directional propagation
Interactive parameter exploration through Dash
The project explores how ignition location, vegetation density, and environmental conditions influence wildfire spread patterns.

Features
Interactive wildfire simulation dashboard
Real-time fire propagation visualization
Wind direction and wind strength controls
Adjustable ignition point
Multiple landscape maps
Burned area tracking over time
Satellite-image-based terrain processing
Directional spread modeling
Interactive map click ignition
Mathematical Model
The landscape is discretized into a spatial grid where each cell can be:

Susceptible (unburned)
Burning
Burned
Fire propagation depends on:

Local burning neighbors
Vegetation density
Wind direction and strength
Stochastic ignition probability
Minimum burn duration
The ignition probability follows a stochastic exponential model:

python
p_ignite = 1.0 - np.exp(-k * beta_eff * N)
where:

k controls global spread intensity
beta_eff represents vegetation flammability
N is the effective number of burning neighbors
Wind introduces anisotropic propagation by biasing spread toward the wind direction.

Satellite Terrain Processing
Vegetation density is extracted from RGB satellite imagery using color-based vegetation indices.

The model processes terrain maps to generate spatially varying flammability coefficients:

python
veg = 2 * G - R - B
Higher vegetation density corresponds to greater wildfire susceptibility.

Dashboard Interface
The dashboard was built using:

Dash
Plotly
NumPy
PIL
scikit-image
Users can:

Start, pause, and restart simulations
Modify wind conditions
Change ignition points
Explore different landscapes
Monitor burned proportion over time
Visualize directional fire spread
Simulation Examples
Wildfire propagation
The simulation captures:

Wind-driven fire fronts
Terrain heterogeneity
Directional spread patterns
Burned area evolution
Spatial ignition dynamics
Example outputs and GIFs are included in this repository.

Research Poster
This repository also includes the research poster developed for the project:

fire_spread_marta.pdf
The poster presents:

Model formulation
Validation against real wildfire spread
Environmental parameter analysis
Simulation results
Conclusions and limitations
Repository Structure
text
wildfire_simulation/
│
├── wildfire_dash_2.py
├── requirements.txt
├── california.png
├── fire_spread_marta.pdf
├── README.md
└── simulation outputs / GIFs
Installation
Clone the repository:

bash
git clone https://github.com/candelaberzal/wildfire_simulation.git
cd wildfire_simulation
Install dependencies:

bash
pip install -r requirements.txt
Running the Dashboard
Run the application locally:

bash
python wildfire_dash_2.py
Then open the local Dash server in your browser.

Technologies Used
Python
NumPy
Dash
Plotly
scikit-image
PIL
Future Improvements
Potential extensions include:

More realistic atmospheric dynamics
Real weather integration
Terrain elevation effects
Parallelized simulation
GPU acceleration
Probabilistic calibration with historical wildfire data
Authors
Candela Berzal Lapuente
Marta Merino Martín
Alejandra Sancho Martín

IE University

Notes
This project was developed for academic and research purposes as part of coursework in mathematical modeling and computational simulation.
