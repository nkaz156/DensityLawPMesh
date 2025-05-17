# DensityLawPMesh
Meshing library for OpenFOAM designed to simplify the process of generating high quality meshes for any geometry, but especially dirty geometry.

There's nothing here yet, this is just a passion project and a way for me to hone my C++ skills, after a semester of wanting to pull my hair out dealing with snappyHexMesh and cfMesh.
Since it will be built on the OpenFOAM framework, meshes can be used in any CFD porgram OpenFOAM can export to.

## Planning information:
- Distributes points based on distance to a part surface using either varying density Poisson Disk Sampling or density based Centroidal Voronoi Tesselation to generate polyhedral cells.
- _Should_ obviate the need for a bunch of mesh quality controls and iterative refinement (except for the CVT point distribution)
- Should be easily modifiable to support boundary layer addition
- Should be callable by solvers that support adaptive mesh refinement, and should only modify points in the refinement field.
- Anisotropy should be should be supported, both in cartesian coordinates and in "radial" and "tangential" coordinates (to create boundary layers), so a unified algorithm can handle all the tesselation.
- No blockMesh needed. Import geometry and define a freestreeam bounding box or import geometry with a bounding box.

## Possibilities:
 - [ ] **Long term** Option to work with CAD geometry (step files through OpenCASCADE)
 - [ ] Support for cfMesh .fms files
