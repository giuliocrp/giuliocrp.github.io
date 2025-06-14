---
title: "Cemosis Internship"
excerpt: "Exa-MA WP1 - Terrain Mesh Generation Internship<br/><img src='/images/portfolio-3/portfolio-3-cover.png'>"
collection: portfolio
---

# Exa-MA WP1 - Terrain Mesh Generation Internship

## Objective
During my internship, I focused on improving the terrain mesh generation process for urban energy simulations as part of the **Exa-MA**[^1] project at **Cemosis**[^2]. The goal was to optimize the 3D geometric reconstruction of urban landscapes by generating constrained triangulated meshes aligned with contour lines, reducing unnecessary complexity in flat areas.


# Exa-MA WP1 - Terrain Mesh Generation Internship

## Objective
During my internship, I focused on improving the terrain mesh generation process for urban energy simulations as part of the **Exa-MA**[^1] project at **Cemosis**[^2]. The goal was to optimize the 3D geometric reconstruction of urban landscapes by generating constrained triangulated meshes aligned with contour lines, reducing unnecessary complexity in flat areas.


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
    - A real-world terrain mesh generated using elevation data from the **Mapbox Terrain-RGB API**[^3]. This high-resolution mesh captures the detailed topography of Grenoble.

<img width="587" alt="generated-gps" src="/images/portfolio-3/generated-grenoble-16.png">


### 2. Contour Line Generation
- Implemented a method to generate and constrain terrain meshes along contour lines:

<img width="401" alt="contour-gps" src="/images/portfolio-3/contour-strasbourg-16-1.png">


### 3. Re-Triangulation
- Using the **CGAL**[^4] library, the contour-constrained meshes were re-triangulated:

<img width="570" alt="constrained-gps" src="/images/portfolio-3/constrained-grenoble-16-1.png">

<img width="732" alt="constrained-gps-side" src="/images/portfolio-3/constrained-grenoble-15-1.png">


## Impact and Future Work
The developed framework successfully reduces mesh complexity, making large-scale urban energy simulations more computationally efficient. Future work could involve merging multiple tiles for broader terrain coverage, optimizing performance for larger datasets, and integrating urban elements like buildings and vegetation to create comprehensive 3D urban models.

Read the project report [here](https://feelpp.github.io/ktirio-geom.docs/internship-reports-2024/terrain/index.html).

Download the project presentation [here](http://giuliocrp.github.io/files/portfolio-3/portfolio-3-presentation.pdf).

## References
[^1]: Exa-MA. Methods and Algorithms for Exascale. 2024. Available at: [Exa-MA](https://numpex.org/exama-methods-and-algorithms-for-exascale)
[^2]: Cemosis. Center for Modeling and Simulation in Strasbourg. 2024. Available at: [Cemosis](https://www.cemosis.fr)
[^3]: Mapbox. Mapbox Terrain-RGB v1. Mapbox Documentation. 2024. Available at [Mapbox Terrain-RGB v1](https://docs.mapbox.com/data/tilesets/reference/mapbox-terrain-rgb-v1)
[^4]: CGAL: The Computational Geometry Algorithms Library. 2024. Available at: [CGAL](https://www.cgal.org)


