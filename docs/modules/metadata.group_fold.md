## Description

Samples are frequently grouped to compare intergroup variability (instead of only inter-sample variability). FERMO allows to specify multiple categories of groups (each column in the group metadata file is considered one category), with multiple groups inside each category. For each category, features associated to multiple groups are identified and their relative abundance is calculated as follows:

- For each feature, association to the groups of a category is determined.
- If a feature is detected in two or more groups, user-specified values detected across the samples belonging to each group are summarized via a user-specified algorithm, the values compared pairwise, and the resulting quotient is registered if >= 1.
- This process is repeated for each specified category


## Parameters

- `algorithm`: the algorithm to summarize values across a group with. Possible algorithms are `mean`, `median`, and `maximum` (highest value across samples of a group)
- `value`: specifies the value to be considered: `height` (=intensity) or `area` of feature.


## Limitations

- Groups from different categories are never compared. Only categories inside groups are compared.