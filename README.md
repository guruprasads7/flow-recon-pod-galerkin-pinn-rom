# Flow Field Reconstruction

## Thesis Overview

The aim of this thesis is to analyze and evaluate the performance, efficiency, and applicability of each computational modeling approach. The comparative study includes:

1. **Traditional Dimensionality Reduction Techniques**: Utilizing methods like Singular Value Decomposition (SVD) to perform Proper Orthogonal Decomposition (POD) of flow fields.
2. **Physics-Informed Neural Networks (PINNs)**: Integrating physics-based constraints into deep learning models to enhance prediction accuracy and generalization in fluid dynamics.
3. **Hybrid POD-Galerkin PINN ROM**: Combining the strengths of POD and PINNs to develop a robust Reduced Order Model that leverages both data-driven and physics-based methodologies.

## POC Data Source

The dataset used in this thesis includes detailed flow field data around a cylinder, a canonical problem in fluid dynamics. This data is crucial for implementing and testing each computational approach. Access the data at [Data-Driven Science & Engineering by Steven L. Brunton and J. Nathan Kutz](http://dmdbook.com/).

## Current Implementations

### 1. POD Reconstruction POC

This implementation uses Singular Value Decomposition (SVD) to perform Proper Orthogonal Decomposition (POD) of flow fields. It includes setting an `energy_threshold` to determine the number of modes to retain, thus ensuring a balance between accuracy and computational efficiency. This method is primarily used as a proof of concept for flow field reconstruction.

**Features:**
- Utilizes `numpy.linalg.svd` for decomposition.
- Employs an energy threshold to retain significant modes, which capture a predefined percentage of the flow's energy.
- Aids in understanding the significant features of the flow with reduced computational resources.

### 2. Developing POD Galerkin ROM using RBniCS POC

This approach develops a Reduced Order Model (ROM) using the RBniCS library, tailored for computational fluid dynamics (CFD) applications based on POD techniques.

**Features:**
- Leverages the RBniCS library, which is built on top of the FEniCS project for finite element analysis.
- Implements affine decomposition of the Navier-Stokes equations to enhance simulation efficiency.
- Applies the Galerkin method to project the high-fidelity model onto a lower-dimensional subspace. **Status: Pending Implementation**
