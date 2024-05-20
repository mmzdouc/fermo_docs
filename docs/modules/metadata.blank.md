## Description

Sample blanks (i.e. instrument runs without sample injection) are frequently used to determine molecular features that are not associated with the biological variability of a sample (e.g. background ions, instrument noise). Therefore, blank subtraction is an integral part of metabolomics data processing. The algorithm works as follows:

- Molecular features only observed in samples designated as “BLANK” are considered blank-associated
- Molecular features only observed in non-blank samples are never considered blank-associated
- For each feature observed in both non-blank and blank samples, a user-specified feature value (height or area) across “non-blank” and “blank” samples is compared using an user-specified algorithm. If the resulting quotient is greater than a user-specified ratio (fold-change), the feature is considered NOT blank-associated, else, it is considered blank-associated. This allows to retain features that are detected in sample blanks due to column retention/bleed.

## Parameters

- `algorithm`: algorithm to summarize value over non-blank samples and sample blanks (mean, median, maximum (highest value across non-blanks/blanks)).
- `value`: specifies type of value to be considered (height or area)
- `factor`: determines subtraction of features detected in both blank and non-blank samples.
