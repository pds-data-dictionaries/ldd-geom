# Geometry Local Data Dictionary (LDD)

The Geometry dictionary contains all geometric information in the label.

Steward: [PDS Geosciences Node](https://pds-geosciences.wustl.edu/)

## Current Source

Only one LDD source version is kept such that it can be managed by github.

- [1.D.0.0](src)

## Versions

A Local Data Dictionary (LDD) is built for selected versions of the [PDS4 Information Model](https://pds.nasa.gov/pds4/doc/im/).
The build process insures compatiblity of the LDD with the core information model.

## Builds

This LDD has been built for the following versions of the PDS4 information models.

- [1.D.0.0](build/1.D.0.0)
- [1.B.1.0](build/1.B.1.0)
- [1.B.0.0](build/1.B.0.0)

## Notes

Each build is generated using the [lddtool](https://pds.nasa.gov/tools/about/ldd/) specific to a version of the [PDS4 Information Model](https://pds.nasa.gov/datastandards/documents/im/). The build command used is:

```
lddtool -lpsnJ ldd-file.xml
```

