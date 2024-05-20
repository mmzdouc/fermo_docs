## Description

This module filters molecular features that do not fit specified cutoff settings. It has been observed that under certain circumstances, a large part of molecular features can be attributed to instrument noise [Samples 2023](https://doi.org/10.1021/acs.analchem.2c04632). Therefore, FERMO allows to filter irrelevant molecular features from the analysis:

- For a given range of relative signal height/height (0-1.0, relative to the feature with the highest intensity), molecular features that are not inside this range in at least one sample are discarded
- For a given range of relative signal area (0-1.0, relative to the feature with the highest area), molecular features that are not inside this range in at least one sample are discarded


## Parameters

- `filter_rel_int_range`: specifies the range of relative intensity to retain in analysis
- `filter_rel_area_range`: specifies the range of relative area to retain in analysis
