## Description

[MS2Query](https://github.com/iomega/ms2query) is a machine-learning based annotation algorithm which allows for exact and analog matching. MS2Query provides its own spectral library derived from the GNPS library. FERMO can accept a pre-calculated MS2Query results file for annotation, but can also run the MS2Query algorithm on its own. In the latter case, the MS2Query results file is written in the output directory and can be used in consecutive runs to prevent redundant calculation. For more information on the algorithm, see the MS2Query documentation.

## Parameters

- `score_cutoff`: minimum score in `ms2query_model_prediction` to consider a match

## Limitations

- Given the large number of reference spectra in this library, MS2Query annotation is relatively slow, with an estimated 1-2 seconds of calculation time per feature.