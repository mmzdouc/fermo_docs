## Description

The “quantitative-percentage” module takes phenotype/bioactivity data where samples have a measured percentage of bioactivity/phenotype at a specified concentration. Multiple measurements can be specified for each sample, and multiple assays (each with a determined concentration) can be provided. The algorithm works as follows:

- All percentage values lower than zero are set to zero.
- Duplicate measurements per sample are summarized with a user-specified algorithm (mean or median)
- For each feature occurring in more than two active samples, the area per sample and the percentage measurement per sample are extracted and z-transformed 
- The transformed areas and percentages are correlated using the Pearson correlation.
- The resulting p-value is corrected for multiple hypothesis testing using the Bonferroni-method (p-value * number of tested features)
- If both correlation coefficient and p-value meet a user-specified cutoff, the phenotype information is assigned and the tested feature is considered bioactivity-associated

This method assumes a positive linear correlation between phenotype (percentage) and concentration (area of feature). 


## Parameters

- `sample_avg`: specifies the algorithm to summarize multiple measurements per sample for same assay. Possible algorithms are `mean` and `median`.
- `value`: specifies value per feature to be correlated with percentage. Only `area` is currently allowed.
- `algorithm`: specifies the statistical algorithm to use. Only `pearson` is currently allowed.
- `p_val_cutoff`: Maximum Bonferroni-corrected p-value to consider, with zero disabling cutoff filtering for both p-value and coefficient.
- `coeff_cutoff`: Minimum correlation coefficient to consider, with zero disabling cutoff filtering for both p-value and coefficient.
