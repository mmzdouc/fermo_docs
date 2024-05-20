*FERMO* is dashboard app for metabolomics data analysis. It aims to make the annotation and prioritization of relevant metabolites **convenient**, **reproducible**, and **comprehensive**.

#### Supported data types

- **LC-MS(/MS)** metabolomics data
- **Genomics** data
- **Phenotype** (bioactivity) data
- Environmental/group **(meta)data**

#### Supported analyses

- Molecular feature **filtering**
- Spectral similarity (molecular) **networking**
- Feature **annotation** and **identification**
- **Phenotype** data correlation
- Determination of **fold changes**
- Calculation of **prioritization scores**

## Using *FERMO* in data analysis

In a typical metabolomics analysis, hundreds or thousands of molecular features are routinely detected. This wealth of information makes it challenging to manually identify and prioritize relevant molecules for further investigations. *FERMO* supports the prioritization task by an automated annotation pipeline, calculation of prioritization scores, and an intuitive graphical user interface. This allows to rapidly inspect data, formulate hypotheses, and determine relevant features.


### Benefits of *FERMO*
- **Interface**: *FERMO* comes as intuitive dashboard allowing to prioritize data with a few clicks.
- **Flexibility**: *FERMO* only requires a feature peaktable - everything else is optional.
- **Tool integration**: *FERMO* integrates many different tools into a single pipeline.
- **Modularity**: *FERMO* is fully modular and allows for easy enabling/disabling of functionality.
- **Reproducibility**: *FERMO*'s input parameter file allows for reproducible analysis runs.
- **Prioritization scores**: *FERMO* combines the individual modules in meta-scores useful for prioritization.


### Limitations of *FERMO*

- **Pre-processing**: *FERMO* does not accept raw data and needs a pre-processed feature peaktable.
- **Data compatibility**: *FERMO* needs DDA-ESI-LC-MS(/MS) input data. Currently, accepted input file formats are limited.
- **Scale**: *FERMO*'s interface is not intended to display a large number (>100) of samples. While there is not fixed threshold, users intending to run large-scale analyses are advised to look into running `fermo_core` locally. 