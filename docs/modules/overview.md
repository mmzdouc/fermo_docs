*FERMO* functionality is separated in modules: each module has a certain functionality and takes certain parameters that modify its behavior. All modules are optional and can be switched on/off as desired.

Modules can be separated into two types:

- `core_modules`: run by default and must be turned off explicitly
- `additional_modules`: are disabled by default (e.g. because they need specific input files) and must be turned on explicitly

In the *FERMO* GUI, these parameters can be set using the input forms. If you are running *FERMO* in command line mode, see the section [Parameters](../home/core.parameters.md) for information about setting up the parameter file.

### `core_modules`

- [Adduct Annotation](annotation.adduct.md)
- [Neutral Loss Annotation](annotation.loss.md)
- [Fragment Annotation](annotation.fragment.md)
- [Spectral Similarity (Molecular) Networking](networking.md)

### `additional_modules`

- [Feature Filtering](filter.feature.md)
- [MS/MS Filtering](filter.msms.md)
- [Blank Assignment](metadata.blank.md)
- [Group Assignment](metadata.group_fold.md)
- [Phenotype Qualitative](phenotype.qualitative.md)
- [Phenotype Quantitative-Percentage](phenotype.quant-percent.md)
- [Phenotype Quantitative-Concentration](phenotype.quant-concentr.md)
- [Spectral Library Annotation](annotation.userlib.md)
- [MS2Query Annotation](annotation.ms2query.md)
- [antiSMASH KnownClusterBlast Annotation](annotation.as_kcb.md)
- [Feature Scores Calculation](scores.features.md)
- [Sample Scores Calculation](scores.samples.md)

