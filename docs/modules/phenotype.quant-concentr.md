## Description

The “quantitative-concentration” module takes phenotype/bioactivity data where samples are specified at the minimum inhibitory concentration (concentration/dilution at which a phenotypic signal was still observed). Samples inactive at any concentration are specified with zero. The algorithm works as follows:

- Duplicate measurements per sample are summarized with a user-specified algorithm (mean or median)
- For each feature occurring in more than two active samples, the area per sample and the concentration measurement per sample are extracted.
- The concentration are converted to their reciprocals (1 / measurement) or left at zero if the concentration was zero
- Both areas and reciprocals of concentration are z-transformed
- The transformed areas and percentages are correlated using the Pearson correlation
- The resulting p-value is corrected for multiple hypothesis testing using the Bonferroni-method (p-value * number of tested features)
- If both correlation coefficient and p-value meet a user-specified cutoff, the phenotype information is assigned and the tested feature is considered bioactivity-associated

## Parameters

- `sample_avg`: specifies the algorithm to summarize multiple measurements per sample for same assay. Possible algorithms are `mean` and `median`.
- `value`: specifies value per feature to be correlated with concentration. Only `area` is currently allowed.
- `algorithm`: specifies the statistical algorithm to use. Only `pearson` is currently allowed.
- `p_val_cutoff`: Maximum Bonferroni-corrected p-value to consider, with zero disabling cutoff filtering for both p-value and coefficient.
- `coeff_cutoff`: Minimum correlation coefficient to consider, with zero disabling cutoff filtering for both p-value and coefficient.


## Limitations

- This method assumes that the prerequisites with regard to sample reproducibility are met (see [Input/Output](../home/input_output.md)).
- This method assumes a negative linear relationship between phenotype (concentration) and concentration (area of feature) - the lower the minimal inhibitory concentration, the higher the concentration.
- This method does not take into account any synergistic or quenching effects