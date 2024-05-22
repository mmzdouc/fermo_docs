## Description

This module performs filtering of MS/MS fragmentation spectra of features. MS/MS spectra regularly contain fragments caused by instrument noise, which obfuscate and prolongate the analysis. Therefore, it is recommended to remove low-intensity fragments.

By default, all peaks `10` Da around the precursor m/z are removed from the MS/MS spectrum before MS/MS filtering takes place. Since these fragments are unlikely to be associated with the fragmentation of the molecule, this also takes place if `rel_int_from` was set to `0.0`.

## Parameters

- `rel_int_from`: specifies the minimum relative intensity to retain fragments. If 0.0, all fragments are retained. A value of 0.01 would remove all fragments with an intensity of less than 1% of the most intense fragment.
