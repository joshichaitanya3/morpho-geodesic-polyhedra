[comment]: # (Morpho gd module help file)
[version]: # (0.1.1)

# GD
[taggd]: # (gd)

The `gd` module provides a small script to generate arbitrary geodesic
polyhdra with a given frequency `(m,n)`. 

`GD` is the primary object provided by the module. It is initialized
with two natural numbers, corresponding to the (m,n) values. 

```
var gd = GD(3,2) // Initialize the (3,2) geodesic polyhedron
```

It supports two optional arguments:
* `verbose` : bool indicating whether the script should print progress. `true` by defualt
* `triangulate`: bool indicating whether to triangulate the polyhedron
  vertices. `true` by default. If the connectivity is unnecessary,
  having this variable be `false` can save time.  

The initialization in the line above determines the vertex positions of
the (m,n) lattice on a unit sphere and triangulates it if `triangulate`
is `true`. 

The `GD` object has a few useful functions/methods:

[showsubtopics]: # (subtopics)

## mesh
[tagmesh]: # (mesh)

The `mesh` method returns the Morpho mesh corresponding to the
polyhedron.

```
var mesh = gd.mesh()
```

## export
[tagexport]: # (export)

The `export` method saves the mesh in the Morpho `.mesh` format.

```
gd.export() // Saves the mesh as "GD_3_2.mesh"
```

## exportvtk
[tagexportvtk]: # (exportvtk)

The `exportvtk` method saves the mesh in the Morpho `.vtk` format.

```
gd.exportvtk() // Saves the mesh as "GD_3_2.vtk"
```

## plotCoordNum
[tagplotcoordnum]: # (plotcoordnum)

The `plotCoordNum` method plots the coordination number field on the
mesh

```
gd.plotCoordNum() 
```

## minimizeThomson
[tagminimizethomson]: # (minimizethomson)

The `minimizeThomson` method defines a Thomson problem treating the
vertices as charged particles and minimizes the electrostatic potential.

## plotThomsonPotential
[tagplotthomsonpotential]: # (plotthomsonpotential)

The `plotThomsonPotential` method plots the Thomson potential on the
for the current vertex positions. This can be used without minimizing
the potential as well.

```
gd.plotThomsonPotential()
```
