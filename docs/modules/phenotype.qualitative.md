## Description

The “qualitative” module takes phenotype/bioactivity data where samples are specified in a binary format: “positive” or “negative”. The algorithm works as follows:

- Features exclusively detected in the “positive” samples are considered phenotype/bioactivity-associated. 
- Features exclusively detected in the “negative” samples are considered NOT phenotype/bioactivity-associated. 
- For features detected in both “positive” and “negative” samples, a user-specified feature value (height or area) across “positive” and “negative” samples is compared using an user-specified algorithm. If the resulting quotient is greater than a user-specified ratio (fold-change), the feature is considered phenotype/bioactivity-associated; else, it is not. This allows to retain features that may be bioactivity-associated but are present in subinhibitory concentrations in the “negative” samples (lack of phenotypic/bioactivity readout).

## Parameters

- `factor`: the user-specified ratio (fold change) to differentiate features detected in both “positive” and “negative” samples.
- `value`: the value used in the determination of the quotient: either “height” or “area”.
- `algorithm`: the algorithm to summarize values over “positive” and “negative” samples. Currently possible algorithms are “mean”, “median”, and “minmax”. The latter takes the **lowest** value across “positive” samples and the **highest** value across “negative” samples
