## Description

For feature annotation, *FERMO* accepts results created by [MS2Query](https://github.com/iomega/ms2query), a machine-learning based annotation algorithm. 
MS2Query comes with its own spectral library derived from the GNPS library and can do exact and/or analog matching.
For compatibility with *FERMO*, the MS2Query results file must come with an additional column `id` that matches the IDs of the molecular features (see [here](../home/input_output.md#ms2query-results-file) for details).
For more information on the algorithmm see the [MS2Query Documentation](https://github.com/iomega/ms2query).

## Parameters

- `score_cutoff`: minimum score in `ms2query_model_prediction` to consider a match to be valid. Matches with a score lower than `score_cutoff` are not considered for molecular feature annotation.