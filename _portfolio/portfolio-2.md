---
title: "Academic Project"
excerpt: "Symbolic Regression<br/><img src='/images/portfolio-2/portfolio-2-cover.png'>"
collection: portfolio
---

# Symbolic Regression

## Objective

This project develops a reduced-order model for the 1D advection-diffusion PDE with Gaussian initial conditions using convolutional autoencoders for compression and SINDy-like symbolic regression for interpretable decoding.

## Key Components

### 1. PDE Formulation

Advection-diffusion equation in non-conservative form:
$$
\frac{\partial u}{\partial t} + a \frac{\partial u}{\partial x} - D \frac{\partial^2 u}{\partial x^2} = 0,
$$
with Gaussian initial condition:
$$
u(x, 0) = \frac{1}{\sigma_0 \sqrt{2\pi}} \exp\left(-\frac{(x-\mu_0)^2}{2\sigma_0^2}\right).
$$

Analytical solution derives ODEs:

$$
\frac{\partial \mu}{\partial t} = \alpha
$$
$$
\frac{\partial \sigma^2}{\partial t} = 2D
$$


### 2. Numerical Solver

Spatial: Upwind for advection, centered finite difference for diffusion. Temporal: Explicit Euler. Stability via CFL and diffusion conditions.


### 3. Data Generation

Vary

$$
\mu_0 \in \{0.3, 0.5, 0.7\}, \quad \sigma_0 \in \{0.05, 0.1, 0.15\}.
$$

Solve PDE over $[0,0.3]$, collect snapshots.


### 4. Convolutional Autoencoder

Compresses snapshots to 2D latent space.

<img width="587" alt="Autoencoder Structure" src="/images/portfolio-2/autoencoder-cnn-structure.png">


### 5. Symbolic Decoder (SINDy-Like)





Download the project report [here](http://giuliocrp.github.io/files/portfolio-2/portfolio-2-report.pdf).

Download the project presentation [here](http://giuliocrp.github.io/files/portfolio-2/portfolio-2-presentation.pdf).