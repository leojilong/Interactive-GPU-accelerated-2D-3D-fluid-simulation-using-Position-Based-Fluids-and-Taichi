# Position-Based Fluid Simulation

An interactive 2D and 3D fluid simulation system based on the **Position-Based Fluids (PBF)** method, with GPU acceleration and real-time user interaction.

This project was developed as part of **CSC417** at the University of Toronto by **Hanlin Zhou and Long Ji**. The implementation follows the algorithms introduced in *Position Based Fluids* by Miles Macklin and Matthias Müller (2013).

## Overview

Fluid simulation can be computationally expensive, making interactive simulation and visualization challenging. This project explores how **position-based constraints and GPU acceleration** can be used to simulate fluid behavior efficiently while allowing users to interact with the simulation in real time.

The project includes:

* Interactive **2D fluid simulation**
* GPU-accelerated **3D fluid simulation**
* User-controlled fluid movement
* 3D particle output for external visualization
* Support for rendering simulation results in tools such as **Blender** and **Houdini**

## Demo

### 2D Simulation

![2D Fluid Simulation](2d-demo.gif)

The 2D simulation supports interactive control of fluid movement using the keyboard.

### 3D Simulation

![3D Fluid Simulation](3d-demo.gif)

The 3D simulation runs on the GPU and exports particle positions as PLY files for visualization and rendering in external tools.

## Technical Approach

The simulation is based on the **Position-Based Fluids** method, which represents the fluid as particles and enforces density constraints through position corrections.

The implementation uses:

* **Python** for simulation logic
* **Taichi 0.7.0** for GPU-accelerated computation
* **CUDA** for GPU execution
* **PLY** for exporting 3D simulation results

The GPU-based implementation allows computationally intensive particle calculations to run efficiently and supports interactive simulation.

## Interaction

### 2D Simulation

Run:

```bash
python Position_Based_Fluid.py
```

Use:

* `A` — Move fluid left
* `D` — Move fluid right

### 3D Simulation

Run:

```bash
python PBF3D.py
```

Use:

* `A` — Move fluid left
* `D` — Move fluid right
* `W` — Move fluid up
* `S` — Move fluid down

The 3D simulation exports PLY files to:

```text
./3d_ply
```

These files can be imported into visualization and 3D rendering software such as Blender or Houdini.

## Requirements

* 64-bit Python 3
* Taichi 0.7.0
* CUDA-compatible GPU recommended for 3D simulation

To run on CPU instead, change:

```python
ti.init(arch=ti.gpu)
```

to:

```python
ti.init(arch=ti.cpu)
```

CPU execution is not recommended for the 3D simulation due to its computational requirements.

## Applications

Position-based fluid simulation can support interactive visualization and simulation scenarios in areas such as:

* Computer graphics and animation
* Interactive game and simulation environments
* Scientific and engineering visualization
* Virtual and immersive environments

This project focuses on the underlying simulation and visualization technology rather than a domain-specific application.

## Reference

Macklin, M., & Müller, M. (2013). *Position Based Fluids.*

https://mmacklin.com/pbf_sig_preprint.pdf

## Video

[Project Demonstration](https://youtu.be/yp1B_HC5wLo)

