---
title: "Academic Project"
excerpt: "ExaMA WP1 - Vegetation<br/><img src='/images/portfolio-4/portfolio-4-cover.png'>"
collection: portfolio
---

# Exa-MA WP1 - Vegetation

## Objective

This academic project, part of the **HiDALGO2** initiative, focuses on integrating vegetation—specifically trees—into 3D urban models to enhance thermal and energy simulations for improved building energy efficiency and indoor air quality. Conducted at **Cemosis** (Center for Modeling and Simulation, Strasbourg – CNRS spinoff) within the University of Strasbourg, the work leverages **OpenStreetMap** data and **CGAL** algorithms to generate and incorporate tree models into urban terrain meshes, with a primary focus on Strasbourg, France.

## Key Components

### 1. Data Acquisition

Tree data was sourced from **OpenStreetMap** using the **Overpass API** and **cURL** to query nodes tagged as "natural=tree" within a specified bounding box. A configurable config.json file allows users to define parameters such as the bounding box, origin coordinates, altitude, level of detail (LOD), default height range, default genus, input building mesh, and output options.

### 2. Tree Library

A library of 13 tree models in .stl format was created from SketchUp's 3D Warehouse. Additional 28 genera were categorized to match similar models for broader coverage. Visualizations of a sample of models using MeshLab:

<div style="display: flex; justify-content: space-around; flex-wrap: wrap; gap: 10px;">
  <img src="/images/portfolio-4/tree-abies.png" alt="Tree Abies" style="width: 45%; max-width: 300px;">
  <img src="/images/portfolio-4/tree-aesculus.png" alt="Tree Aesculus" style="width: 45%; max-width: 300px;">
  <img src="/images/portfolio-4/tree-catalpa.png" alt="Tree Catalpa" style="width: 45%; max-width: 300px;">
  <img src="/images/portfolio-4/tree-liquidanbar.png" alt="Tree Liquidanbar" style="width: 45%; max-width: 300px;">
</div>

### 3. Dataset

The primary dataset is a .stl file of Strasbourg's city center, containing ~120,959 vertices and ~273,178 facets, representing terrain and buildings.

<img width="587" alt="Strasbourg Mesh" src="/images/portfolio-4/strasbourg-mesh-1.png">

### 4. Alpha Wrapping

The CGAL Alpha Wrapping algorithm generates watertight meshes by shrink-wrapping a Delaunay triangulation around input data, balancing tightness and complexity with parameters alpha and offset.


### 5. Tree Model Generation

Reference meshes are pre-wrapped at LODs 0-3 (alpha: 0.1, 20, 50, 100; offset: 600). Trees are scaled and translated using CGAL Affine Transformations to match height and position.

Ginkgo examples at each LOD:

<div style="display: flex; justify-content: space-around; flex-wrap: wrap; gap: 10px;">
  <img src="/images/portfolio-4/gingko-lod0.png" alt="Gingko LOD 0" style="width: 45%; max-width: 300px;">
  <img src="/images/portfolio-4/gingko-lod1.png" alt="Gingko LOD 1" style="width: 45%; max-width: 300px;">
  <img src="/images/portfolio-4/gingko-lod2.png" alt="Gingko LOD 2" style="width: 45%; max-width: 300px;">
  <img src="/images/portfolio-4/gingko-lod3.png" alt="Ginko LOD 3" style="width: 45%; max-width: 300px;">
</div>


## Results

### Model Integration

Trees integrated into Strasbourg models, e.g., Place de la République.

<img width="587" alt="Strasbourg Mesh with Trees" src="/images/portfolio-4/mesh-strasbourg-enhanced1.png">

<img width="587" alt="Strasbourg Mesh with Trees" src="/images/portfolio-4/mesh-strasbourg-enhanced2.png">


## Impact and Future Work

The framework enhances urban simulations by incorporating vegetation, reducing computational complexity while maintaining realism. Future enhancements include seasonal leaf variations (clustering leaves) and shading simulations using Feel++ for PDE-based ray tracing.

Download the project report [here](http://giuliocrp.github.io/files/portfolio-4/portfolio-4-report.pdf).

Download the project presentation [here](http://giuliocrp.github.io/files/portfolio-4/portfolio-4-presentation.pdf).