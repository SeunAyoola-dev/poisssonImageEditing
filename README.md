# poisssonImageEditing
This repository contains a Python implementation of several image processing operations based on the landmark paper “Poisson Image Editing” by Pérez et al. (https://www.cs.jhu.edu/~misha/Fall07/Papers/Perez03.pdf)
The project demonstrates how solving Poisson equations enables seamless blending, texture flattening, and gradient-based image manipulation.

# Features 
## 1. Poisson Solver (Gauss-Seidel Method) 
A core component of the project: 
- Solves the Poisson equation with Dirichlet boundary conditions
- Uses Gauss-Seidel iteration
- Supports optional guidance fields for gradient mixing
- Automatically stops when convergence tolerance is reached

Forms the foundation of all editing operations in the notebook 

# Gradient Field Computation
The notebook implements functions to extract gradient fields, including:
- Sobel-based gradient estimation
- Laplacian filters
- Edge-preserving preprocessing
- Gradient import/mixing (from source → target)
  
These gradients determine how texture and structure transfer between images.

# Texture Flattening 
Implements the texture flattening technique from the paper
- Supresses fine-scale texture
- Preserves strong edges
- Works by modifying and reintergrating gradient fields
- Solves the Poisson equation to reconstruct a smooth output image

# Gradient Mixing 
Implements the mixed gradients technique
- For each pixel, selects the dominant gradient from source or target
- Produces seamless blending
- Useful for cloning and object insertion

# Region Replacement/Reconstruction 
- Removes a region from an image
- Reconstruction using surrounding boundary constraints
- Using Poisson reconstruction to fill missing content smoothly 
