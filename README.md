General information about the CTL course available at https://ctl.polyphys.mat.ethz.ch/

# :wave: PROJECT Diffusion-limited aggregation

Create a (L+1) *x* (L+1) regular 2D grid filled with zeros. 
A so-called seed particle (unit cell with value 1) is added in the center of the grid, and it will remain there forever. Then *N* so-called random walkers (cells with value 2) start at a specified radius $\approx$ *R < L/2* from the center. The walkers make, one after the other, a single random step in any of the 8 directions. They are added to the 1-cluster (and change their value to 1, and do not move anymore) if they touch it (if they have a joint edge). At startup, the 1-cluster contains only the seed particle, but the 1-cluster (black in the figure below) grows with time. If a random walker comes close to the edge of the grid, it is simply removed. The 1-cluster is considered complete as soon as any of its members center coordinates exceeds the distance *R* from the center, i.e., as soon as one of the black square centers resides outside red dashed circle of radius *R*.

<img src="https://www.complexfluids.ethz.ch/images/PROJECT-DLA-2.png" width="40%">

The resulting cluster has a lot of holes and exhibits a branching behavior. This is understandable: if we add random walkers at the distance of the center and let them wander, there is a greater chance they will be added to the branches of the cluster as it grows.

To quantify this observation, we can find the fractal dimensionality of the cluster. This parameter arises from the scaling rules: consider the mass of the objects. For a straight line mass $m$ is proportional to $r$, and for disk proportional to $r^2$, where $r$ is the distance from the seed particle. Therefore, consider $m = c r^d$, with so-called fractal dimension $d$, or equivalently, 

$\ln(m)=d \ln(r)+\ln c$

For fractals, we would expect a fractal dimension between 1 and 2.

## Task 1: Implement this model

Typical parameters: $L=401$, $N=3000$, $R=50$. 

## Task 2: Visualize the cluster growth

Visualize the cluster as it grows. You may also display the locations of the walkers. 

## Task 3: Determine the fractal dimension

Perform several growth experiments to obtain good statistics and return the fractal dimensions and an error bar. The relative error should be below 2%.  
