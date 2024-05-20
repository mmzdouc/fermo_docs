## Description

This module compares molecular features against a user-provided (targeted) spectral library. The matching algorithm works as follows:

- For each feature, its MS/MS fragmentation spectrum is matched pairwise with each library spectrum, using one or more different algorithms described below. 
- For the `modified cosine` algorithm, library matches are only retained if feature and library spectra share a minimum number of matched peaks within a certain fragment tolerance, reach a cutoff score, and are inside a maximum precursor mass difference.
- For the [MS2DeepScore](https://github.com/matchms/ms2deepscore) algorithm, library matches are only retained if feature and library spectra reach a certain cutoff score and are inside a maximum precursor mass difference.


## Parameters `modified cosine`

- `fragment_tol`: the absolute tolerance for matching two MS/MS fragments, in m/z units.
- `min_nr_matched_peaks`: minimum number of fragments that must be matched between two MS/MS fragmentation spectra.
- `score_cutoff`: minimum score to consider a match
- `max_precursor_mass_diff`: maximum allowed difference between precursor m/z of feature and library m/z.

## Parameters `ms2deepscore`

- `score_cutoff`: minimum score to consider a match
- `max_precursor_mass_diff`: maximum allowed difference between precursor m/z of feature and library m/z.

## Limitations

- Spectral library matching is relatively slow (especially using the MS2DeepScore algorithm). Ideally, a targeted spectral library should be provided. For a more general library, see MS2Query annotation.
