# morpho-geodesic-polyhedra
## Morpho module to generate arbitrary geodesic polyhedra with frequency (m,n)

This repository provides a small script to generate arbitrary geodesic
polyhdra with a given frequency `(m,n)`. You will need Morpho installed
to run the script. You can find instructions for the installation
[here](https://github.com/Morpho-lang/morpho).

## Installation

You can get the code by cloning this repository or downloading the
source code. You can use the module by copying the files
[gd.morpho](gd.morpho) and [tools.morpho](tools.morpho) in your working directory and importing it in your
scripts as follows:

```
import "gd.morpho"
```

The [tools.morpho](tools.morpho) file is used by the `gd` module and doesn't
need a separate import.

## Usage

A basic usage example can be found under [example.morpho](example.morpho). 

## The `GD` object and its functions

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

### mesh

The `mesh` method returns the Morpho mesh corresponding to the
polyhedron.

```
var mesh = gd.mesh()
```

### export

The `export` method saves the mesh in the Morpho `.mesh` format.

```
gd.export() // Saves the mesh as "GD_3_2.mesh"
```

### exportvtk

The `exportvtk` method saves the mesh in the Morpho `.vtk` format.

```
gd.exportvtk() // Saves the mesh as "GD_3_2.vtk"
```

### plotCoordNum

The `plotCoordNum` method plots the coordination number field on the
mesh

```
gd.plotCoordNum() 
```

![Plot of the geodesic polyhdron with color showing the coordination
number of the vertices.](coordNum.png "Coordination Number Plot")

### minimizeThomson

The `minimizeThomson` method defines a Thomson problem treating the
vertices as charged particles and minimizes the electrostatic potential.

### plotThomsonPotential

The `plotThomsonPotential` method plots the Thomson potential on the
for the current vertex positions. This can be used without minimizing
the potential as well.

```
gd.plotThomsonPotential()
```

![Plot of the geodesic polyhdron with color showing the Thomson
potential value.](thomson.png "Thomson potential")