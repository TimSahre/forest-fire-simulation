# Forest Fire Simulation 🌲🔥

![Forest Fire Simulation](forest_fire_with_metrics.gif)

This project simulates forest growth and fires using a grid-based approach, leveraging Python and visualization tools like Matplotlib. The simulation dynamically visualizes forest states, including tree growth, fires, clouds, and ash, and is highly configurable through a YAML file.

## Features

- **Grid-based Simulation**: Represents forests, fires, water, and more on a 2D grid.
- **Dynamic Wind and Temperature**: Wind direction and daily temperature influence fire spread.
- **Configurable Parameters**: Easily customize the simulation via a YAML configuration file.
- **Visualization**: Animates the forest lifecycle and outputs it as a GIF.
- **Reproducible Environment**: Includes a Conda environment file for easy setup.

---

## Installation

### Prerequisites
Ensure you have the following installed:
- **Anaconda/Miniconda** for managing the Python environment
- **Git** for cloning the repository

### Steps

1. **Clone the Repository**:
   ```bash
   git clone https://github.com/your_username/forest-fire-simulation.git
   cd forest-fire-simulation
   ```

2. **Set Up the Environment**:
   Create the Conda environment using the provided `environment.yml` file:
   ```bash
   conda env create -f environment.yml
   ```

3. **Activate the Environment**:
   ```bash
   conda activate forest_fire_simulation
   ```

4. **Run the Simulation**:
   Launch Jupyter Notebook to execute the simulation:
   ```bash
   jupyter notebook
   ```
   Open the `forest_fire_simulator.ipynb` file and run the cells.

---

## Files in the Repository

### 1. `forest_fire_simulator.ipynb`
The main Jupyter Notebook containing the implementation of the simulation.

### 2. `config.yml`
A YAML configuration file where you can set:
   - Grid dimensions
   - Fire and tree growth probabilities
   - Wind direction, temperature range, and noise
   - Visualization colors and animation settings

### 3. `environment.yml`
Defines the Conda environment, specifying all dependencies needed to run the simulation.

---

## Configuring the Simulation

Modify the `config.yml` file to adjust parameters:

```yaml
simulation:
  grid:
    height: 100  # Grid height
    width: 100   # Grid width
  probabilities:
    fire: 0.0001  # Probability of lightning strike
    tree_growth: 0.05  # Probability of tree growth
  terrain:
    bedrock_fraction: 0.01  # Fraction of bedrock in the grid
    water_fraction: 0.02  # Fraction of water in the grid
  ash:
    lifetime: 20  # Steps before ash disappears
  temperature:
    average: 20  # Average daily temperature
    amplitude: 5  # Temperature fluctuation range
    noise: 2  # Random noise in temperature
  wind:
    direction: random  # Wind direction ('random' or specific: N, S, E, W, etc.)
  forest:
    fraction: 0.05  # Fraction of the grid covered by forest

animation:
  frames: 400  # Total animation frames
  interval: 100  # Interval between frames (ms)
  output_file: 'forest_fire_with_metrics.gif'  # Output file name
  fps: 10  # Frames per second

visualization:
  colors:
    - steelblue   # Water
    - grey        # Bedrock
    - black       # Ash
    - lightgreen  # Grass
    - forestgreen # Trees
    - red         # Fire
    - white       # Clouds
  colormap_bounds: [-3, -2, -1, 0, 1, 2, 3, 4]  # Boundaries for colormap
```

---

## Output
The simulation generates a dynamic **GIF file** named `forest_fire_with_metrics.gif`, which illustrates the progression of the forest fire, tree growth, and cloud movement over time.

---
