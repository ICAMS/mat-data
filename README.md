# mat-data – Material Data Repository for Crystal Plasticity

Repository for material parameters intended to be used with crystal plasticity constitutive models. Validated crystal-plasticity material parameter sets: individual YAML entries
under [entries/](entries/), JSON schemas under [schemas/](schemas/). Currently supported crystal plasticity models are [ICAMS CP-UMAT](https://github.com/ICAMS/Crystal_Plasticity_UMAT.git) and [DAMASK phenopowerlaw](https://damask-multiphysics.org/3.0.0-alpha8/documentation/file_formats/material_yaml/phase/phenopowerlaw.html).  
A mapping table for YAML keywords to Abaqus `PROPS` for use with ICAMS CP-UMAT is provided in [mapping\_icams\_cp.csv](mapping_icams_cp.csv). 

**This repository contains no code** — only data and documentation. Validation
and export logic lives in the separate
[mat-data-handler](https://github.com/ICAMS/mat-data-handler) repository/package,
which fetches this repository's content over the network.

## Adding a material

Copy `entries/template.yaml` to `entries/<stable-material-key>.yaml`,
e.g. `entries/austenite_316l_room_temperature.yaml`. Use lowercase letters,
digits, and underscores for stable keys. Each file contains one material
object without an outer database key. Use descriptive keys to distinguish
calibrations of the same alloy. Replace the example values and reference with
measured or calibrated data, including the conditions under which they apply.

Use spaces for indentation, string keys, unquoted numeric values, and quoted
text identifiers. Put machine-readable units and provenance in fields;
comments are for author guidance. Avoid duplicate keys, custom YAML tags, and
aliases. Do not store grain-specific Euler angles in the material database.

See [CONTRIBUTING.md](CONTRIBUTING.md) for the review/CI process.

## How consumers access this data

`mat-data-handler` (or any other tool) reads this repository's content
directly from GitHub at a pinned ref (tag, branch, or commit) — via a tarball
download (`https://codeload.github.com/ICAMS/mat-data/tar.gz/<ref>`) or a
`git clone` — cached locally after the first fetch. There is no
`pyproject.toml` here and nothing to `pip install`; this repo is consumed as
data, not as a package.

## Releases

 * Initial release: v2026.9.15

## License

Data is licensed under [CC-BY-4.0](LICENSE) (see attribution requirements).
