## Description

This module performs feature annotation by matching neutral losses (=precursor m/z - fragments) against a library of annotated neutral losses (adapted from [Kersten et al 2011](https://doi.org/10.1038/nchembio.684), [Kersten et al 2013](https://doi.org/10.1073/pnas.1315492110), Correa&Niessen 2017 (ISBN:9781118500187)). Such neutral losses can indicate functional groups present in the molecule and help with identification. The annotation algorithm works as follows:

- For each feature, iterate through neutral losses and compare them against a library of annotated neutral losses.
- If the values of a neutral loss and a library neutral loss match (are inside a specified mass deviation), annotate the feature.


## Parameters

- `mass_dev_ppm`: the maximum allowed mass deviation difference to constitute a match
- `nonbiological`: allows to specify if neutral losses characteristic to non-biological molecules (synthetic chemicals) should be included in the search. This may lead to spurious matches.


## Limitations

- Neutral loss matches can often be spurious (a neutral loss can correspond to many different molecule substructures) or can result from random noise. Therefore, they must not be trusted blindly.
