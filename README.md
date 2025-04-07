# CPFEH

Crystal Plasticity Finite Element Homogenization model for
[Dyalog APL](https://www.dyalog.com/)

## Example

The script `eg.apls` runs several example simulations using a randomly
generated microstructure with Fe-gamma and Fe-alpha grains with
boundary conditions of uniaxial tension.

Expected output:

        grains      steps       ∆time       iter        iterc       seconds
            50          10   5.00E¯2           410         413        1.10
           100          10   5.00E¯2           390         393        1.72
           150          10   5.00E¯2           410         413        4.81
           200          10   5.00E¯2           410         413        6.74
           250          10   5.00E¯2           410         413        9.06
            50         100   5.00E¯2          3972        4292       19.91
            50         500   5.00E¯2         19245       21493      103.64
            50        1000   5.00E¯2         37894       42642      181.07   r.csv  tex.csv  f.csv

Timings (in the last column) may vary. Plotting the strain and stress
in the generated file `r.csv` should result in the following tensile
diagram:

![Tensile diagram](eg.png)

## CPFEH Model

The model uses a gradient descent method to solve the self-consistent
polycrystal formalism. Grain interaction is determined such that each
grain is in a relaxed-constraints relationship with respect to its
direction dependent environment.

### Grain Behaviour

Each grain is assumed to have elasto-viscoplastic behaviour. Plastic
strain is determined using the strain rate sensitivity approach.

#### Slip Systems

Plastic strain happens by shear along crystallographic directions
on crystallographic planes. Each slip system is thus defined by
a direction (Burges vector), and the normal to the plane.

#### Strain Hardening

Accumulated shear causes the increment of the resolved shear stress
according to the Voce law.

### Grain-Environment Interaction

The environment of each grain along each direction is determined
depending on the distribution measured experimentally. It is assumed
that the neighbour grains will have relaxed the components not
associated with the common face.

### Self-Consistent Formalism

Localisation tensors allow to correlate macrospic and grain stresses.
These magnitudes are also related according to the interaction equation.
Using an iterative method, a solution is found that satisfies all
these conditions.

### Microstructural Update

After a solution has been found for each simulation step, the
microstructure of the material is updated. The strain hardening law
is used to increase the resolved shear stress, grains are rotated
depending on plastic deformation and angular velocity, and deformation
tensors are modified.

## Input and Output

The `CPFEH` dyadic operator takes as right operand convergence parameters
and as left operand the target error and maximum number of steps. As right
argument it takes the microstructure, including materials (which can be
read from json files with the `MATERIAL` function), orientations,
topology (given as common areas in each direction) and volume. It returns
a table with time, strain, stress and number of iterations to solve stress
and to reach self-consistency.
