# bmi-geospatial-fortran

The Fortran specification for an example
[Basic Model Interface](https://bmi.readthedocs.io) extension
for geospatial data.

The SIDL describing the interface for this example extension:
```java
package csdms version 0.0.1 {
  interface bmi_geo {

    int initialize(in string config_file);
    int get_grid_coordinate_names(in int grid, out array<string, 1> names);
    int get_grid_coordinate_units(in int grid, out array<string, 1> units);
    int get_grid_coordinate(in int grid, int string coordinate, in array<double, 1> values);
    int get_grid_crs(in int grid, out string name);
  }
}
```

Like the [Fortran specification for the core BMI](https://github.com/csdms/bmi-fortran),
the code in this repository
is used to define an abstract type, *bmi_geo*,
that is intended to be overridden by a concrete type in an implementation.
The *bmi_geo* type is encapsulated in a module, *bmigeof*,
and built into a library, *libbmigeof*.
