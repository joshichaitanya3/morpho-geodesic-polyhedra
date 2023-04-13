# morpho-geodesic-polyhedra
## Morpho module to generate arbitrary geodesic polyhedra with frequency (m,n)

## Installation and Prerequisites

To install this package, clone this repository onto your computer in any convenient place:

    git clone https://github.com/joshichaitanya3/morpho-geodesic-polyhedra.git

then add the location of this repository to your .morphopackages file.

    echo PACKAGEPATH >> ~/.morphopackages 

where PACKAGEPATH is the location of the git repository. 

## Usage 

A basic usage example can be found under the [examples](./examples) folder. 

Some of its functionality is highlighted here, but full documentation is found under [help](./share/help/gd.md), 
which is also available as inline help in Morpho upon installation.

## The `GD` object and its functions

`GD` is the primary object provided by the module. It is initialized
with two natural numbers, corresponding to the (m,n) values. 

```
import gd
var gd = GD(3,2) // Initialize the (3,2) geodesic polyhedron
```

The `GD` object has a few useful functions/methods:

### mesh

The `mesh` method returns the Morpho mesh corresponding to the
polyhedron.

```
var mesh = gd.mesh()
```

### plotCoordNum

The `plotCoordNum` method plots the coordination number field on the
mesh

```
gd.plotCoordNum() 
```

![Plot of the geodesic polyhdron with color showing the coordination
number of the vertices.](assets/coordNum.png "Coordination Number Plot")

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
potential value.](assets/thomson.png "Thomson potential")