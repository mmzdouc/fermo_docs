## Description

This module performs feature annotation by matching single MS/MS fragments against a library of annotated MS/MS fragments. Therefore, matches can help to annotate features and identify molecules. The annotation algorithm works as follows:

- For each feature, iterate through fragments and compare them against a library of annotated fragments.
- If the m/z values of a fragment and a library fragment match (are inside a specified mass deviation), annotate the feature.


## Parameters

- `mass_dev_ppm`: the maximum allowed mass deviation difference to constitute a match

## Limitations

- Fragment matches can often be spurious (a single fragment m/z can correspond to many different molecule substructures) or can result from random noise. Therefore, they must not be trusted blindly.
- Currently, only positive ion mode fragments are supported.
- Currently, only y2- and b2 fragments resulting from (proteinogenic) peptides are supported (all calculated as [M+H]+ adducts). More information can be found on [fermo_core_extras](https://github.com/mmzdouc/fermo_core_extras). 