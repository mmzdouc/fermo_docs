## Description

The “qualitative” module takes qualitative phenotype/bioactivity data. 
Samples are either considered “positive” or “negative”. 
The algorithm works as follows:

- Features exclusively detected in the “positive” samples are considered phenotype/bioactivity-associated. 
- Features exclusively detected in the “negative” samples are considered NOT phenotype/bioactivity-associated. 
- For features detected in both “positive” and “negative” samples, a user-specified feature value (height or area) across “positive” and “negative” samples is compared using a user-specified algorithm. If the resulting quotient is greater than a user-specified ratio (fold-change), the feature is considered phenotype/bioactivity-associated; else, it is not. This allows to retain features that may be bioactivity-associated but are present in sub-inhibitory concentrations in the “negative” samples (lack of phenotypic/bioactivity readout). The fold-change is then registered as the phenotype score.

## Parameters

- `factor`: the user-specified ratio (fold change) to differentiate features detected in both “positive” and “negative” samples.
- `value`: the value used in the determination of the quotient: either “height” or “area”.
- `algorithm`: the algorithm to summarize values over “positive” and “negative” samples. Currently possible algorithms are “mean”, “median”, and “minmax”. The latter takes the **lowest** value across “positive” samples and the **highest** value across “negative” samples


## Limitations

- Contrary to [Quantitative-Percentage](../modules/phenotype.quant-percent.md) and [Quantitative-Concentration](../modules/phenotype.quant-concentr.md), this module does not perform predictions - it rather excludes features that are unlikely to be associated with the observed phenotype.
- This method assumes that the prerequisites with regard to sample reproducibility are met (see [Input/Output](../home/input_output.md)).
