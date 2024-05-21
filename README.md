# PINN
Keras examples of physics informed neural networks (PINNs)

## Basic Concepts
PINNs are artificial neural networks (ANNs) designed to solve partial differential equations (PDEs) and physics problems by incorporating machine learning process. Unlike traditional data-driven neural networks (NNs) that rely solely on data for training, PINNs leverage (experimental) data discovery and underlying physical modeling of the problem.

### Key Components of PINNs
#### Neural Network Architecture
- PINNs use standard NN architectures, typically composed of multiple layers of neurons with activation functions.
- The input to the network includes the spatial and temporal coordinates (e.g., $x$,$y$,$z$ and $t$) and potentially other parameters.
- The output of the network is the solution to the PDE (e.g., the wave function $u$, velocity $\vec{v}$ and pressure $p$).
#### Physical Laws and PDEs
- PINNs incorporate the governing equations (e.g., Navier-Stokes equations for fluid dynamics, wave equation for wave propagation, diffusion equation for heat transfer) into the training process.
- These equations are embedded into the loss function of the neural network, ensuring that the network’s predictions satisfy the physical laws.
#### Loss Function
The loss function in PINNs consists of two main components:
- **Data Loss**: The discrepancy between the neural network's predictions and the available experimental or synthetic data.
- **PDE Residual Loss**: The discrepancy between the network's predictions and the PDE's governing equations. This is typically calculated using automatic differentiation to compute derivatives required by the PDE.

The total loss is a weighted sum of the data loss and the PDE residual loss.
#### Training Process

- The NN is trained using gradient-based optimization methods (e.g., Adam, SGD) to minimize the total loss.

- During training, the network learns to approximate the solution to the PDE while satisfying the physical constraints imposed by the governing equations.
### Advantages of PINNs
- **Incorporation of Prior Knowledge**: By embedding physical laws into the training process, PINNs can leverage prior knowledge about the system, potentially reducing the need for large amounts of training data.
- **Generalization**: PINNs are capable of generalizing well to different initial and boundary conditions due to their adherence to physical laws.
- **Solving Complex Problems**: PINNs can be used to solve high-dimensional PDEs and complex systems where traditional numerical methods may be computationally expensive or infeasible.

By integrating the physics of the problem directly into the neural network training process, PINNs provide a powerful tool for solving complex PDEs and modeling physical systems. This approach can be particularly useful when data is sparse or when seeking solutions that adhere strictly to known physical laws.

## Example Use Case:
1. [Wave equation](./notebooks/wave_equation.ipynb)
2. [2D Incompressible Navier-Stokes Equations](./notebooks/2d_ns_equation.ipynb)