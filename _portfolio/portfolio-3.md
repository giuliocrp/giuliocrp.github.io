---
title: "CNRS Internship"
excerpt: "Exa-MA WP1 - Terrain Mesh Generation Internship<br/><img src='/images/portfolio-3/portfolio-3-cover.png'>"
collection: portfolio
---

# Exa-MA WP1 - Terrain Mesh Generation Internship

## Objective
During my internship, I focused on improving the terrain mesh generation process for urban energy simulations as part of the **Exa-MA**[^1] project at **Cemosis**[^2] a **CNRS** spin-off.

The goal was to build a C++ application to optimize 3D terrain mesh generation for finite element simulations in urban energy modeling. The pipeline sourced elevation data for any given geographical area using the **Mapbox Terrain-RGB API**[^3], processed it and used **CGAL**[^4] to create a Delaunay mesh constrained to contour lines.

## Key Components

### 1. Terrain Mesh Generation

- **Lambda-Generated Meshes:**
  - **Half-Sphere Terrain:**
    - This mesh was generated using a lambda function representing a half-sphere:

<img width="587" alt="generated-lambda-1" src="/images/portfolio-3/generated-lambda-1.png">

  - **Wave-Like Terrain:**
    - Another lambda-generated mesh with a wave-like surface:

<img width="587" alt="generated-lambda-2" src="/images/portfolio-3/generated-lambda-2.png">

- **GPS Data-Driven Meshes:**
  - **Grenoble, France (Zoom Level 16):**
    - A real-world terrain mesh generated using elevation data from the **Mapbox Terrain-RGB API**. This high-resolution mesh captures the detailed topography of Grenoble.

<img width="587" alt="generated-gps" src="/images/portfolio-3/generated-grenoble-16.png">


### 2. Contour Line Generation
- Implemented a method to generate and constrain terrain meshes along contour lines:

<img width="401" alt="contour-gps" src="/images/portfolio-3/contour-strasbourg-16-1.png">


### 3. Re-Triangulation
- Using the **CGAL** library, the contour-constrained meshes were re-triangulated:

<img width="570" alt="constrained-gps" src="/images/portfolio-3/constrained-grenoble-16-1.png">

<img width="732" alt="constrained-gps-side" src="/images/portfolio-3/constrained-grenoble-15-1.png">


## Impact and Future Work
The pipeline developed during this internship successfully reduced mesh complexity making large-scale urban energy simulations more computationally efficient.

Future work could involve merging multiple tiles for broader terrain coverage, optimizing performance for larger datasets, integrating urban elements such as buildings and vegetation to create more comprehensive models.

Read the project report [here](https://feelpp.github.io/ktirio-geom.docs/internship-reports-2024/terrain/index.html).

## References
[^1]: Exa-MA. Methods and Algorithms for Exascale. 2024. Available at: [Exa-MA](https://numpex.org/exama-methods-and-algorithms-for-exascale)
[^2]: Cemosis. Center for Modeling and Simulation in Strasbourg. 2024. Available at: [Cemosis](https://www.cemosis.fr)
[^3]: Mapbox. Mapbox Terrain-RGB v1. Mapbox Documentation. 2024. Available at [Mapbox Terrain-RGB v1](https://docs.mapbox.com/data/tilesets/reference/mapbox-terrain-rgb-v1)
[^4]: CGAL: The Computational Geometry Algorithms Library. 2024. Available at: [CGAL](https://www.cgal.org)