# LBsmoothing
Code is in branch master!
Laplace-Beltrami mesh enhancement Python3 code for unstructured meshes.
The mesh is currently assumed to be quadrilaterals with node and element 
numbers beginning with 1 instead of 0 as in C++. The enhancement method 
is described in Hansen, Douglass, Zardecki, Mesh Enhancement: Selected 
Elliptic Methods, Foundations, and Applications, Imperial College Press, 2005
specifically in sections 9.2 and 9.3. There is also a matplotlib capability 
to plot initial and final unstructured meshes.

To execute the code, simply download it and type: python3 LB.py.
A test problem will run (one of 2 tests in the code; remove """ - in 2 places and 
place them around the other test data).  Execution runs through the first plot, 
then pauses until the plot is deleted. Execution continues in a similar vein 
through the plotting of the final mesh. When trhe plot is removed, execution 
terminates.  Both plots are saved as .pdf files. There are 2 constants in the 
function LBsmoother which may be adsjusted: epsilon and maxIter which are used
to stop the solution iteration.

There are 4 variables needed to setup a new mesh problem: dofs, edofs, coords,
and bdyNodes. This nomenclature is from calfem, a mesh generation code available
from github.com.  It is based in the solid mechanics area.
  1. dofs - (degrees of freedom) contains the node numbers with a "marker", here "0" is used.
     Node numbering should first list all boundary nodes; then the internal
     nodes.
  2. edof - (element degrees of freedom) contains the node numbers for each
     element (assuming counterclockwise listing)
  3. coords - contains the x,y coordinate pairs for each node as given in dofs
  4. bdyNodes - lists the boundary node numbers, the first BN nodes in dofs
     where BN is the number of boundary nodes.
