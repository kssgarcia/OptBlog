---
title: OptTopology reference
weight: 1
next: /docs
prev: /docs/getting-started
---

# Utils package

## Utils.BESO_utils module

#### `adjacency_nodes(nodes, els)`

Create an adjacency matrix for the elements connected to each node.

**Parameters:**

- `nodes`: Array with model nodes.
- `els`: Array with model elements.

**Returns:**

- `adj_nodes`: Adjacency elements for each node.

#### `center_els(nodes, els)`

Calculate the center of each element.

**Parameters:**

- `nodes`: Array with model nodes.
- `els`: Array with model elements.

**Returns:**

- `centers`: Center of each element.

#### `del_node(nodes, els, loads, BC)`

Restrict nodes degrees of freedom that aren't used and free up the nodes that are in use.

**Parameters:**

- `nodes`: Array with model nodes.
- `els`: Array with model elements.
- `loads`: Array with model loads.
- `BC`: Boundary conditions nodes.

**Returns:**

*No explicit return.*

#### `is_equilibrium(nodes, mats, els, loads)`

Check if the system is in equilibrium.

**Parameters:**

- `nodes`: Array with model nodes.
- `mats`: Array with model materials.
- `els`: Array with model elements.
- `loads`: Array with model loads.

**Returns:**

- `equil`: Variable `True` when the system is in equilibrium and `False` when it doesn't.

#### `postprocessing(nodes, mats, els, bc_array, disp)`

Compute the nodes displacements, strains, and stresses.

**Parameters:**

- `nodes`: Array with model nodes.
- `mats`: Array with model materials.
- `els`: Array with model elements.
- `bc_array`: Boundary conditions array.
- `disp`: Static solve.

**Returns:**

- `disp_complete`: Displacements at elements.
- `strain_nodes`: Strains at elements.
- `stress_nodes`: Stresses at elements.

#### `preprocessing(nodes, mats, els, loads)`

Compute IBC matrix and the static solve.

**Parameters:**

- `nodes`: Array with model nodes.
- `mats`: Array with model materials.
- `els`: Array with model elements.
- `loads`: Array with model loads.

**Returns:**

- `bc_array`: Boundary conditions array.
- `disp`: Static displacement solve.
- `rh_vec`: Vector of loads.

#### `protect_els(els, nels, loads, BC)`

Compute a mask array with the elements that don't must be deleted.

**Parameters:**

- `els`: Array with model elements.
- `nels`: Number of elements.
- `loads`: Array with model loads.
- `BC`: Boundary conditions nodes.

**Returns:**

- `mask_els`: Array with the elements that don't must be deleted.

#### `sensitivity_els(nodes, mats, els, mask, UC)`

Calculate the sensitivity number for each element.

**Parameters:**

- `nodes`: Array with model nodes.
- `mats`: Array with model materials.
- `els`: Array with model elements.
- `mask`: Mask of optimal structure.
- `UC`: Displacements at nodes.

**Returns:**

- `sensi_number`: Sensitivity number for each element.

#### `sensitivity_filter(nodes, centers, sensi_nodes, r_min)`

Perform the sensitivity filter.

**Parameters:**

- `nodes`: Array with model nodes.
- `sensi_nodes`: Array with nodal sensitivity.
- `centers`: Array with center of elements.
- `r_min`: Minimum distance.

**Returns:**

- `sensi_els`: Sensitivity of each element with filter.

#### `sensitivity_nodes(nodes, adj_nodes, centers, sensi_els)`

Calculate the sensitivity of each node.

**Parameters:**

- `nodes`: Array with model nodes.
- `adj_nodes`: Adjacency matrix of nodes.
- `centers`: Array with center of elements.
- `sensi_els`: Sensitivity of each element without filter.

**Returns:**

- `sensi_nodes`: Sensitivity of each node.

#### `volume(els, length, height, nx, ny)`

Compute volume.

**Parameters:**

- `els`: Array with model elements.
- `length`: Length of the beam.
- `height`: Height of the beam.
- `nx`: Number of elements in the x direction.
- `ny`: Number of elements in the y direction.

**Return:**

- `V`: Float, Volume of the structure.

## Utils.ESO_utils module

### `del_node(nodes, els)`

Restrict nodes degrees of freedom that aren’t been used.

**Parameters:**

- `nodes`: Array with model nodes.
- `els`: Array with model elements.

**Returns:**

*No explicit return.*

### `is_equilibrium(nodes, mats, els, loads)`

Check if the system is in equilibrium.

Get from: [https://github.com/AppliedMechanics-EAFIT/SolidsPy/blob/master/solidspy/solids_GUI.py](https://github.com/AppliedMechanics-EAFIT/SolidsPy/blob/master/solidspy/solids_GUI.py)

**Parameters:**

- `nodes`: Array with model nodes.
- `mats`: Array with model materials.
- `els`: Array with model elements.
- `loads`: Array with model loads.

**Returns:**

- `equil`: Variable `True` when the system is in equilibrium and `False` when it doesn’t.

### `postprocessing(nodes, mats, els, bc_array, disp)`

Compute the nodes displacements, strains, and stresses.

Get from: [https://github.com/AppliedMechanics-EAFIT/SolidsPy/blob/master/solidspy/solids_GUI.py](https://github.com/AppliedMechanics-EAFIT/SolidsPy/blob/master/solidspy/solids_GUI.py)

**Parameters:**

- `nodes`: Array with model nodes.
- `mats`: Array with model materials.
- `els`: Array with model elements.
- `bc_array`: Boundary conditions array.
- `disp`: Static solve.

**Returns:**

- `disp_complete`: Displacements at elements.
- `strain_nodes`: Strains at elements.
- `stress_nodes`: Stresses at elements.

### `preprocessing(nodes, mats, els, loads)`

Compute IBC matrix and the static solve.

Get from: [https://github.com/AppliedMechanics-EAFIT/SolidsPy/blob/master/solidspy/solids_GUI.py](https://github.com/AppliedMechanics-EAFIT/SolidsPy/blob/master/solidspy/solids_GUI.py)

**Parameters:**

- `nodes`: Array with model nodes.
- `mats`: Array with model materials.
- `els`: Array with model elements.
- `loads`: Array with model loads.

**Returns:**

- `bc_array`: Boundary conditions array.
- `disp`: Static displacement solve.

### `protect_els(els, loads, BC)`

Compute a mask array with the elements that don’t must be deleted.

**Parameters:**

- `els`: Array with model elements.
- `loads`: Array with model loads.
- `BC`: Boundary conditions nodes.

**Returns:**

- `mask_els`: Array with the elements that don’t must be deleted.

### `sensi_el(nodes, mats, els, UC)`

Calculate the sensitivity number for each element.

**Parameters:**

- `nodes`: Array with model nodes.
- `mats`: Array with model materials.
- `els`: Array with model elements.
- `UC`: Displacements at nodes.

**Returns:**

- `sensi_number`: Sensitivity number for each element.

### `strain_els(els, E_nodes, S_nodes)`

Compute the elements strains and stresses.

Get from: [https://github.com/AppliedMechanics-EAFIT/SolidsPy/blob/master/solidspy/solids_GUI.py](https://github.com/AppliedMechanics-EAFIT/SolidsPy/blob/master/solidspy/solids_GUI.py)

**Parameters:**

- `els`: Array with model elements.
- `E_nodes`: Strains at nodes.
- `S_nodes`: Stresses at nodes.

**Returns:**

- `E_els`: Strains at elements.
- `S_els`: Stresses at elements.

### `volume(els, length, height, nx, ny)`

Volume calculation.

**Parameters:**

- `els`: Array with model elements.
- `length`: Length of the beam.
- `height`: Height of the beam.
- `nx`: float
- `ny`: float

**Return:**

- `V`: Float, Volume of the beam.

## Utils.MMA_truss_utils module

### `del_node(nodes, els)`

Restrict nodes degrees of freedom that aren’t been used.

Get from: [https://github.com/AppliedMechanics-EAFIT/SolidsPy/blob/master/solidspy/solids_GUI.py](https://github.com/AppliedMechanics-EAFIT/SolidsPy/blob/master/solidspy/solids_GUI.py)

**Parameters:**

- `nodes`: Array with model nodes.
- `els`: Array with model elements.

**Returns:**

*No explicit return.*

### `fem_sol(nodes, els, mats, loads)`

Compute the FEM solution for a given problem.

**Parameters:**

- `nodes`: Array with nodes.
- `els`: Array with element information.
- `mats`: Array with material information. We need a material profile for each element for the optimization process.
- `loads`: Array with loads.

**Returns:**

- `disp`: Displacement for each node.
- `UC`: Complete displacement vector.
- `rhs_vec`: Load vector.

### `gradient(lamb, v_max, q_o, L_j, v_j, alpha, x_max)`

Calculates the gradient of the objective function for a given lambda.

**Parameters:**

- `lamb`: Lambda value.
- `v_max`: Maximum possible value for v.
- `q_o`: Initial value of q.
- `L_j`: Lower bound for x.
- `v_j`: Coefficient for the x term.
- `alpha`: Minimum possible value for x.
- `x_max`: Maximum possible value for x.

**Returns:**

- `grad`: Gradient of the objective function.

### `grid_truss(length, height, nx, ny)`

Generates a grid of nodes and elements representing a truss structure.

**Parameters:**

- `length`: Length of the truss.
- `height`: Height of the truss.
- `nx`: Number of nodes in the x direction.
- `ny`: Number of nodes in the y direction.

**Returns:**

- `nodes`: Array of nodes.
- `elements`: Array of elements.
- `nels`: Total number of elements.
- `x`: x-coordinates of the nodes.
- `y`: y-coordinates of the nodes.

### `is_equilibrium(nodes, elements, mats, loads)`

Check if the system is in equilibrium.

Get from: [https://github.com/AppliedMechanics-EAFIT/SolidsPy/blob/master/solidspy/solids_GUI.py](https://github.com/AppliedMechanics-EAFIT/SolidsPy/blob/master/solidspy/solids_GUI.py)

**Parameters:**

- `nodes`: Array with model nodes.
- `elements`: Array with model elements.
- `mats`: Array with model materials.
- `loads`: Array with model loads.

**Returns:**

- `equil`: Variable `True` when the system is in equilibrium and `False` when it doesn’t.

### `lengths(els, nodes)`

Compute element’s lengths.

**Parameters:**

- `els`: Array with elements information.
- `nodes`: Array with nodes information.

**Returns:**

- `lengths`: Array with nodes information.

### `objective_function(lamb, r_o, v_max, q_o, L_j, v_j, alpha, x_max)`

Calculates the value of the objective function for a given lambda.

**Parameters:**

- `lamb`: Lambda value.
- `r_o`: Initial value of r.
- `v_max`: Maximum possible value for v.
- `q_o`: Initial value of q.
- `L_j`: Lower bound for x.
- `v_j`: Coefficient for the x term.
- `alpha`: Minimum possible value for x.
- `x_max`: Maximum possible value for x.

**Returns:**

- `obj`: Value of the objective function.

### `plot_truss(nodes, elements, mats, stresses, tol=1e-05)`

Plots a truss and encodes the stresses in a colormap.

**Parameters:**

- `nodes`: Array of nodes.
- `elements`: Array of elements.
- `mats`: Array of material properties.
- `stresses`: Array of stresses.
- `tol`: Tolerance for considering a stress as zero, by default 1e-5.

*No explicit return.*

### `plot_truss_del(nodes, elements, mats, stresses)`

Plots a truss with all elements colored red, regardless of stress.

**Parameters:**

- `nodes`: Array with model nodes.
- `elements`: Array with model elements.
- `mats`: Array of material properties.
- `stresses`: Array of stresses.

*No explicit return.*

### `protect_els(els, loads, BC, mask_del)`

Compute a mask array with the elements that don’t must be deleted.

**Parameters:**

- `els`: Array with model elements.
- `loads`: Array with model loads.
- `BC`: Boundary conditions nodes.
- `mask_del`: Mask array with the elements that must be deleted.

**Returns:**

- `mask_els`: Array with the elements that don’t must be deleted.

### `sensi_el(els, mats, nodes, UC)`

Calculate the sensitivity number for each element.

**Parameters:**

- `els`: Array with model elements.
- `nodes`: Array with model nodes.
- `mats`: Array with model materials.
- `UC`: Displacements at nodes.

**Returns:**

- `sensi_number`: Sensitivity number for each element.

### `sparse_assem(elements, mats, nodes, neq, assem_op)`

Assembles the global stiffness matrix using a sparse storing scheme.

**Parameters:**

- `elements`: Array with the number for the nodes in each element.
- `mats`: Array with the material profiles.
- `nodes`: Array with the nodal numbers and coordinates.
- `neq`: Number of active equations in the system.
- `assem_op`: Assembly operator.

**Returns:**

- `stiff`: Array with the global stiffness matrix in a sparse Compressed Sparse Row (CSR) format.

### `x_star(lamb, q_o, L_j, v_j, alpha, x_max)`

Calculates the optimal x value (x_star) for a given lambda.

**Parameters:**

- `lamb`: Lambda value.
- `q_o`: Initial value of q.
- `L_j`: Lower bound for x.
- `v_j`: Coefficient for the x term.
- `alpha`: Minimum possible value for x.
- `x_max`: Maximum possible value for x.

**Returns:**

- `x_star`: Optimal x value (x_star).

## Utils.MMA_utils module

### `gradient(lamb, v_max, q_o, L_j, v_j, alpha, x_max)`

Calculates the gradient of the objective function for a given lambda.

**Parameters:**

- `lamb`: Lambda value.
- `v_max`: Maximum possible value for v.
- `q_o`: Initial value of q.
- `L_j`: Lower bound for x.
- `v_j`: Coefficient for the x term.
- `alpha`: Minimum possible value for x.
- `x_max`: Maximum possible value for x.

**Returns:**

- `grad`: Gradient of the objective function.

### `objective_function(lamb, r_o, v_max, q_o, L_j, v_j, alpha, x_max)`

Calculates the value of the objective function for a given lambda.

**Parameters:**

- `lamb`: Lambda value.
- `r_o`: Initial value of r.
- `v_max`: Maximum possible value for v.
- `q_o`: Initial value of q.
- `L_j`: Lower bound for x.
- `v_j`: Coefficient for the x term.
- `alpha`: Minimum possible value for x.
- `x_max`: Maximum possible value for x.

**Returns:**

- `obj`: Value of the objective function.

### `sensi_el(els, UC, kloc)`

Calculate the sensitivity number for each element.

**Parameters:**

- `els`: Array with model elements.
- `UC`: Displacements at nodes.
- `kloc`: Stiffness matrix of a single element.

**Returns:**

- `sensi_number`: Sensitivity number for each element.

### `sparse_assem(elements, mats, neq, assem_op, kloc)`

Assembles the global stiffness matrix using a sparse storing scheme.

**Parameters:**

- `elements`: Array with the number for the nodes in each element.
- `mats`: Array with the material profiles.
- `neq`: Number of active equations in the system.
- `assem_op`: Assembly operator.
- `kloc`: Stiffness matrix of a single element.

**Returns:**

- `stiff`: Array with the global stiffness matrix in a sparse Compressed Sparse Row (CSR) format.

### `volume(length, height, nx, ny)`

Volume calculation.

**Parameters:**

- `length`: Length of the beam.
- `height`: Height of the beam.
- `nx`: Number of elements in x direction.
- `ny`: Number of elements in y direction.

**Return:**

- `V`: Float, Volume of a single element.

### `x_star(lamb, q_o, L_j, v_j, alpha, x_max)`

Calculates the optimal x value (x_star) for a given lambda.

**Parameters:**

- `lamb`: Lambda value.
- `q_o`: Initial value of q.
- `L_j`: Lower bound for x.
- `v_j`: Coefficient for the x term.
- `alpha`: Minimum possible value for x.
- `x_max`: Maximum possible value for x.

**Returns:**

- `x_star`: Float, Optimal x value (x_star).


## Utils.SIMP_utils module

### `center_els(nodes, els)`

Calculate the center of each element.

**Parameters:**

- `nodes`: Array with model nodes.
- `els`: Array with model elements.

**Returns:**

- `centers`: Centers of each element.

### `density_filter(centers, r_min, rho, d_rho)`

Perform the sensitivity filter.

**Parameters:**

- `centers`: Array with the centers of each element.
- `r_min`: Minimum radius of the filter.
- `rho`: Array with the density of each element.
- `d_rho`: Array with the derivative of the density of each element.

**Returns:**

- `densi_els`: Sensitivity of each element with filter.

### `optimality_criteria(nelx, nely, rho, d_c, g)`

Optimality criteria method.

**Parameters:**

- `nelx`: Number of elements in the x direction.
- `nely`: Number of elements in the y direction.
- `rho`: Array with the density of each element.
- `d_c`: Array with the derivative of the compliance.
- `g`: Volume constraint.

**Returns:**

- `rho_new`: Array with the new density of each element.
- `gt`: Volume constraint.

### `sparse_assem(elements, mats, neq, assem_op, kloc)`

Assembles the global stiffness matrix using a sparse storing scheme.

**Parameters:**

- `elements`: Array with the number for the nodes in each element.
- `mats`: Array with the material profiles.
- `neq`: Number of active equations in the system.
- `assem_op`: Assembly operator.
- `uel`: Python function that returns the local stiffness matrix.
- `kloc`: Stiffness matrix of a single element.

**Returns:**

- `stiff`: Array with the global stiffness matrix in a sparse Compressed Sparse Row (CSR) format.

### `volume(els, length, height, nx, ny)`

Volume calculation.

**Parameters:**

- `els`: Array with model elements.
- `length`: Length of the beam.
- `height`: Height of the beam.
- `nx`: Number of elements in x direction.
- `ny`: Number of elements in y direction.

**Return:**

- `V`: Float, Volume of a single element.

## Utils.beams module

### `beam(L=10, H=10, E=206800000000.0, v=0.28, nx=20, ny=20, dirs=array([], dtype=float64), positions=array([], dtype=float64), n=1)`

This function selects the appropriate beam function to call based on the value of n.

**Parameters:**

- `L`: Beam’s length, by default 10.
- `H`: Beam’s height, by default 10.
- `F`: Vertical force, by default -1000000.
- `E`: Young’s modulus, by default 206.8e9.
- `v`: Poisson’s ratio, by default 0.28.
- `nx`: Number of elements in the x direction, by default 20.
- `ny`: Number of elements in the y direction, by default 20.
- `n`: Selector for the beam function to call, by default 1.

**Returns:**

- `ndarray`: Nodes array returned by the selected beam function.

### `beam_1(L=10, H=10, E=206800000000.0, v=0.28, nx=20, ny=20, dirs=array([], dtype=float64), positions=array([], dtype=float64))`

Make the mesh for a quadrilateral model with cantilever beam’s constraints.

**Parameters:**

- `L`: Length of the beam, by default 10.
- `H`: Height of the beam, by default 10.
- `E`: Young’s modulus, by default 206.8e9.
- `v`: Poisson’s ratio, by default 0.28.
- `nx`: Number of elements in the x direction, by default 20.
- `ny`: Number of elements in the y direction, by default 20.
- `dirs`: An array with the directions of the loads, by default empty array. [[0,1],[1,0],[0,-1]].
- `positions`: An array with the positions of the loads, by default empty array. [[61,30], [1,30], [30, 1]].

**Returns:**

- `nodes`: Array of nodes.
- `mats`: Array of material properties.
- `els`: Array of elements.
- `loads`: Array of loads.

### `beam_2(L=10, H=10, E=206800000000.0, v=0.28, nx=20, ny=20, dirs=array([], dtype=float64), positions=array([], dtype=float64))`

Make the mesh for a quadrilateral model with simply supported beam’s constraints.

**Parameters:**

- `L`: Length of the beam, by default 10.
- `H`: Height of the beam, by default 10.
- `E`: Young’s modulus, by default 206.8e9.
- `v`: Poisson’s ratio, by default 0.28.
- `nx`: Number of elements in the x direction, by default 20.
- `ny`: Number of elements in the y direction, by default 20.
- `dirs`: An array with the directions of the loads, by default empty array. [[0,1],[1,0],[0,-1]].
- `positions`: An array with the positions of the loads, by default empty array. [[61,30], [1,30], [30, 1]].

**Returns:**

- `nodes`: Array of nodes.
- `mats`: Array of material properties.
- `els`: Array of elements.
- `loads`: Array of loads.

## Module contents
