---
title: "Siemens Digital Industries Sofware Internship"
excerpt: "Reactive trajectory planning for robotic operations in an unstructured environment simulated by Tecnomatix Process Simulate<br/><img src='/images/portfolio-1/portfolio-1-cover.png'>"
collection: portfolio
---

# Reactive Trajectory Planning for Robotic Operations in Tecnomatix Process Simulate

## Objective

This internship project, conducted at **Siemens Digital Industries Software** in Toulouse, France, within the **Kineo**[^1]'s **Advanced Robotics Kinematics** (ARK) team, focuses on integrating a reactive trajectory planning system into Tecnomatix **Process Simulate**. The goal is to enable robotic arms to dynamically perceive and avoid obstacles in unstructured environments using real-time RGB-D camera data.

## Key Components

1. **Architectural Design**

A layered architecture was implemented to ensure modularity and performance:

- **UI Layer (C#/WPF)**: A user-friendly dialog for configuring and controlling the reactive system, including camera setup, simulation start/stop, and real-time feedback.

- **Bridge Layer (C++/CLI)**: Acts as a mediator between managed C# code and native C++ components, using wrappers to handle data transfer and command execution.

- **Core Engine (Native C++)**: Manages the simulation loop, event-driven point cloud capture, and integration with Kineo SDKs for collision detection.


2. **Data Acquisition and Processing**

RGB-D cameras simulate sensor input in Process Simulate. Depth buffers are captured at timed intervals during simulation:

- **Point Cloud Generation**: Converts 2D pixels to 3D points using camera intrinsics (focal length, principal point) and applies camera-to-world transformations.


3. **Two-Stage Filtering Algorithm**

To isolate dynamic obstacles:

- **Stage 1: Robot Geometry Filtering**: Removes points within the robot's bounding boxes (e.g., links of a UR5 arm) to eliminate self-occlusion.

- **Stage 2: Static Environment Filtering**: Uses voxel grids to subtract known static elements like bins or floors.

4. **Collision Detection**

Integrates Kineo Collision Detector to check the robot's trajectory against the filtered point cloud, halting simulation upon potential collisions.

## Results

### Model Integration and Validation

The system was tested in a bin-picking scenario. It successfully detects unexpected obstacles, isolates them via filtering, and prevents collisions by stopping the robot.

### Impact and Future Work

This framework advances reactive robotics in simulated environments, improving safety and adaptability in manufacturing. It reduces reliance on predefined paths and supports human-robot collaboration. Future enhancements include full autonomous path replanning (integrating "plan and act" phases), multi-camera support, hardware-in-the-loop validation, and optimizations for denser point clouds.

Read the project report [here](http://giuliocrp.github.io/files/portfolio-1/portfolio-1-report.pdf).

## References
[^1]: [Kineo](https://plm.sw.siemens.com/en-US/plm-components/kineo)