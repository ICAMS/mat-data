# Changelog for mat-data
Repository for material parameters intended to be used with crystal plasticity consitutive models.  


## v2026.9.15

- Initial repository with generic crystal plasticity parameters for ICAMS CP-UMAT
- Values are provided for aluminum, austenite, copper, ferrite, gold and nickel as YAML files in folder `entries`
- Template file for new entries
- New entires will be validated against the JSON schemas provided in folder `schemas`. Current schemas support CP parameters for [ICAMS CP-UMAT](https://github.com/ICAMS/Crystal_Plasticity_UMAT.git) and [DAMASK phenopowerlaw](https://damask-multiphysics.org/3.0.0-alpha8/documentation/file_formats/material_yaml/phase/phenopowerlaw.html)
- Mapping of parameters specified in YAML files to ICAMS CP-UMAT PROPS as defined in mapping\_icams\_cp.csv
