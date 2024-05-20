## Description

This module performs filtering of MS/MS fragmentation spectra of features. MS/MS spectra regularly contain fragments caused by instrument noise, which obfuscate and prolongate the analysis. Therefore, it is recommended to remove low-intensity fragments.

By default, the precursor-m/z and all peaks 10 Da around it are removed from the MS/MS spectrum before analysis takes place.

## Parameters

- `rel_int_from`: specifies the minimum relative intensity to retain fragments. If 0.0, all fragments are retained. A value of 0.01 would remove all fragments with an intensity of less than 1% of the most intense fragment.
