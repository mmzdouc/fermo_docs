The most important element of a `fermo_core` run is the `parameters.json` file, which specifies all files and run parameters. This file is also generated in the background if `fermo gui` is being used. 

The `parameters.json` file follows this [**json-schema**](https://github.com/mmzdouc/fermo_core/blob/main/fermo_core/config/schema.json) and an example can be found [**here**](https://github.com/mmzdouc/fermo_core/blob/main/tests/test_data/test.parameters.json).

`fermo_core` automatically checks the user-provided parameters file and fails with an error message if the formatting is incorrect.

# Specifications `parameters.json`

The `parameters.json` file is separated in three parts:

- `files`: references to input files, paths, and locations
- `core_modules`: modules that are generally applicable and only require a peaktable and MS/MS information (enabled by default)
- `additional_modules`: modules requiring specific input files (disabled by default)

Detailed information on modules and functions of parameters can be found on the **Modules** pages.

## `files` (mandatory)

*Nota bene*: If a filetype is not provided, the corresponding parameter entry must be omitted.

### [`peaktable` (mandatory)](./input_output.md#molecular-feature-peaktable)

<table style="width: 100%;">
 <tr>
  <td style="width: 33.33%;"><b>Key</b></td>
  <td style="width: 33.33%;"><b>Possible Values</b></td>
  <td style="width: 33.33%;"><b>Required</b></td>
 </tr>
 <tr>
  <td style="width: 33.33%;">filepath</td>
  <td style="width: 33.33%;"><i>(the filepath)</i></td>
  <td style="width: 33.33%;">True</td>
 </tr>
 <tr>
  <td style="width: 33.33%;">format</td>
  <td style="width: 33.33%;">mzmine3</td>
  <td style="width: 33.33%;">True</td>
 </tr>
 <tr>
  <td style="width: 33.33%;">polarity</td>
  <td style="width: 33.33%;">positive, negative</td>
  <td style="width: 33.33%;">True</td>
 </tr>
</table>

### [`msms` (optional)](./input_output.md#msms-spectrum-information)

*Nota bene*: By default, fragment peaks with an intensity lower than 0.01 are removed. To disable filtering, set `rel_int_from` to `0.0`

<table style="width: 100%;">
 <tr>
  <td style="width: 25%;"><b>Key</b></td>
  <td style="width: 25%;"><b>Possible Values</b></td>
  <td style="width: 25%;"><b>Required</b></td>
  <td style="width: 25%;"><b>Default</b></td>
 </tr>
 <tr>
  <td style="width: 25%;">filepath</td>
  <td style="width: 25%;"><i>(the filepath)</i></td>
  <td style="width: 25%;">True</td>
  <td style="width: 25%;">N/A</td>
 </tr>
 <tr>
  <td style="width: 25%;">format</td>
  <td style="width: 25%;">mgf</td>
  <td style="width: 25%;">True</td>
  <td style="width: 25%;">N/A</td>
 </tr>
 <tr>
  <td style="width: 25%;">rel_int_from</td>
  <td style="width: 25%;">0.0-1.0</td>
  <td style="width: 25%;">False</td>
  <td style="width: 25%;">0.01</td>
 </tr>
</table>

### [`phenotype` (optional)](./input_output.md#phenotype-bioactivity-data)

<table style="width: 100%;">
 <tr>
  <td style="width: 33.33%;"><b>Key</b></td>
  <td style="width: 33.33%;"><b>Possible Values</b></td>
  <td style="width: 33.33%;"><b>Required</b></td>
 </tr>
 <tr>
  <td style="width: 33.33%;">filepath</td>
  <td style="width: 33.33%;"><i>(the filepath)</i></td>
  <td style="width: 33.33%;">True</td>
 </tr>
 <tr>
  <td style="width: 33.33%;">format</td>
  <td style="width: 33.33%;">qualitative, quantitative-percentage, quantitative-concentration</td>
  <td style="width: 33.33%;">True</td>
 </tr>
</table>

### [`group_metadata` (optional)](./input_output.md#group-metadata)

<table style="width: 100%;">
 <tr>
  <td style="width: 33.33%;"><b>Key</b></td>
  <td style="width: 33.33%;"><b>Possible Values</b></td>
  <td style="width: 33.33%;"><b>Required</b></td>
 </tr>
 <tr>
  <td style="width: 33.33%;">filepath</td>
  <td style="width: 33.33%;"><i>(the filepath)</i></td>
  <td style="width: 33.33%;">True</td>
 </tr>
 <tr>
  <td style="width: 33.33%;">format</td>
  <td style="width: 33.33%;">fermo</td>
  <td style="width: 33.33%;">True</td>
 </tr>
</table>

### [`spectral_library` (optional)](./input_output.md#spectral-library)

<table style="width: 100%;">
 <tr>
  <td style="width: 33.33%;"><b>Key</b></td>
  <td style="width: 33.33%;"><b>Possible Values</b></td>
  <td style="width: 33.33%;"><b>Required</b></td>
 </tr>
 <tr>
  <td style="width: 33.33%;">filepath</td>
  <td style="width: 33.33%;"><i>(the filepath)</i></td>
  <td style="width: 33.33%;">True</td>
 </tr>
 <tr>
  <td style="width: 33.33%;">format</td>
  <td style="width: 33.33%;">mgf</td>
  <td style="width: 33.33%;">True</td>
 </tr>
</table>

### [`ms2query_results` (optional)](./input_output.md#ms2query-results-file)

<table style="width: 100%;">
 <tr>
  <td style="width: 25%;"><b>Key</b></td>
  <td style="width: 25%;"><b>Possible Values</b></td>
  <td style="width: 25%;"><b>Required</b></td>
  <td style="width: 25%;"><b>Default</b></td>
 </tr>
 <tr>
  <td style="width: 25%;">filepath</td>
  <td style="width: 25%;"><i>(the filepath)</i></td>
  <td style="width: 25%;">True</td>
  <td style="width: 25%;">N/A</td>
 </tr>
 <tr>
  <td style="width: 25%;">score_cutoff</td>
  <td style="width: 25%;">0.0-1.0</td>
  <td style="width: 25%;">False</td>
  <td style="width: 25%;">0.7</td>
 </tr>
</table>

### [`as_results` (optional)](./input_output.md#antismash-results)

<table style="width: 100%;">
 <tr>
  <td style="width: 25%;"><b>Key</b></td>
  <td style="width: 25%;"><b>Possible Values</b></td>
  <td style="width: 25%;"><b>Required</b></td>
  <td style="width: 25%;"><b>Default</b></td>
 </tr>
 <tr>
  <td style="width: 25%;">directory_path</td>
  <td style="width: 25%;"><i>(the directory path)</i></td>
  <td style="width: 25%;">True</td>
  <td style="width: 25%;">N/A</td>
 </tr>
 <tr>
  <td style="width: 25%;">similarity_cutoff</td>
  <td style="width: 25%;">0.0-1.0</td>
  <td style="width: 25%;">False</td>
  <td style="width: 25%;">0.7</td>
 </tr>
</table>

## `core_modules` (optional)

### [`adduct_annotation` (optional)](../modules/annotation.adduct.md)

<table style="width: 100%;">
 <tr>
  <td style="width: 25%;"><b>Key</b></td>
  <td style="width: 25%;"><b>Possible Values</b></td>
  <td style="width: 25%;"><b>Required</b></td>
  <td style="width: 25%;"><b>Default</b></td>
 </tr>
 <tr>
  <td style="width: 25%;">activate_module</td>
  <td style="width: 25%;">true, false</td>
  <td style="width: 25%;">True</td>
  <td style="width: 25%;">true</td>
 </tr>
 <tr>
  <td style="width: 25%;">mass_dev_ppm</td>
  <td style="width: 25%;">0-100.0</td>
  <td style="width: 25%;">False</td>
  <td style="width: 25%;">10.0</td>
 </tr>
</table>

### [`neutral_loss_annotation` (optional)](../modules/annotation.loss.md)

<table style="width: 100%;">
 <tr>
  <td style="width: 25%;"><b>Key</b></td>
  <td style="width: 25%;"><b>Possible Values</b></td>
  <td style="width: 25%;"><b>Required</b></td>
  <td style="width: 25%;"><b>Default</b></td>
 </tr>
 <tr>
  <td style="width: 25%;">activate_module</td>
  <td style="width: 25%;">true, false</td>
  <td style="width: 25%;">True</td>
  <td style="width: 25%;">true</td>
 </tr>
 <tr>
  <td style="width: 25%;">mass_dev_ppm</td>
  <td style="width: 25%;">0-100.0</td>
  <td style="width: 25%;">False</td>
  <td style="width: 25%;">10.0</td>
 </tr>
 <tr>
  <td style="width: 25%;">nonbiological</td>
  <td style="width: 25%;">true, false</td>
  <td style="width: 25%;">False</td>
  <td style="width: 25%;">false</td>
 </tr>
</table>

### [`fragment_annotation` (optional)](../modules/annotation.fragment.md)

<table style="width: 100%;">
 <tr>
  <td style="width: 25%;"><b>Key</b></td>
  <td style="width: 25%;"><b>Possible Values</b></td>
  <td style="width: 25%;"><b>Required</b></td>
  <td style="width: 25%;"><b>Default</b></td>
 </tr>
 <tr>
  <td style="width: 25%;">activate_module</td>
  <td style="width: 25%;">true, false</td>
  <td style="width: 25%;">True</td>
  <td style="width: 25%;">true</td>
 </tr>
 <tr>
  <td style="width: 25%;">mass_dev_ppm</td>
  <td style="width: 25%;">0-100.0</td>
  <td style="width: 25%;">False</td>
  <td style="width: 25%;">10.0</td>
 </tr>
</table>

### [`spec_sim_networking` (optional)](../modules/networking.md)

#### `modified_cosine` (optional)

<table style="width: 100%;">
 <tr>
  <td style="width: 25%;"><b>Key</b></td>
  <td style="width: 25%;"><b>Possible Values</b></td>
  <td style="width: 25%;"><b>Required</b></td>
  <td style="width: 25%;"><b>Default</b></td>
 </tr>
 <tr>
  <td style="width: 25%;">activate_module</td>
  <td style="width: 25%;">true, false</td>
  <td style="width: 25%;">True</td>
  <td style="width: 25%;">true</td>
 </tr>
 <tr>
  <td style="width: 25%;">msms_min_frag_nr</td>
  <td style="width: 25%;"> >=1 </td>
  <td style="width: 25%;">False</td>
  <td style="width: 25%;">5</td>
 </tr>
 <tr>
  <td style="width: 25%;">fragment_tol</td>
  <td style="width: 25%;"> >0 </td>
  <td style="width: 25%;">False</td>
  <td style="width: 25%;">0.1</td>
 </tr>
 <tr>
  <td style="width: 25%;">score_cutoff</td>
  <td style="width: 25%;">0.0-1.0</td>
  <td style="width: 25%;">False</td>
  <td style="width: 25%;">0.7</td>
 </tr>
 <tr>
  <td style="width: 25%;">max_nr_links</td>
  <td style="width: 25%;"> >=1 </td>
  <td style="width: 25%;">False</td>
  <td style="width: 25%;">10</td>
 </tr>
 <tr>
  <td style="width: 25%;">maximum_runtime</td>
  <td style="width: 25%;"> >=0 </td>
  <td style="width: 25%;">False</td>
  <td style="width: 25%;">0 (unlimited)</td>
 </tr>
</table>

#### `ms2deepscore` (optional)

<table style="width: 100%;">
 <tr>
  <td style="width: 25%;"><b>Key</b></td>
  <td style="width: 25%;"><b>Possible Values</b></td>
  <td style="width: 25%;"><b>Required</b></td>
  <td style="width: 25%;"><b>Default</b></td>
 </tr>
 <tr>
  <td style="width: 25%;">activate_module</td>
  <td style="width: 25%;">true, false</td>
  <td style="width: 25%;">True</td>
  <td style="width: 25%;">true</td>
 </tr>
 <tr>
  <td style="width: 25%;">msms_min_frag_nr</td>
  <td style="width: 25%;"> >=1 </td>
  <td style="width: 25%;">False</td>
  <td style="width: 25%;">5</td>
 </tr>
 <tr>
  <td style="width: 25%;">score_cutoff</td>
  <td style="width: 25%;">0.0-1.0</td>
  <td style="width: 25%;">False</td>
  <td style="width: 25%;">0.8</td>
 </tr>
 <tr>
  <td style="width: 25%;">max_nr_links</td>
  <td style="width: 25%;"> >=1 </td>
  <td style="width: 25%;">False</td>
  <td style="width: 25%;">10</td>
 </tr>
 <tr>
  <td style="width: 25%;">maximum_runtime</td>
  <td style="width: 25%;"> >=0 </td>
  <td style="width: 25%;">False</td>
  <td style="width: 25%;">0 (unlimited)</td>
 </tr>
</table>

## `additional_modules` (optional)

### [`feature_filtering` (optional)](../modules/filter.feature.md)

<table style="width: 100%;">
 <tr>
  <td style="width: 25%;"><b>Key</b></td>
  <td style="width: 25%;"><b>Possible Values</b></td>
  <td style="width: 25%;"><b>Required</b></td>
  <td style="width: 25%;"><b>Default</b></td>
 </tr>
 <tr>
  <td style="width: 25%;">activate_module</td>
  <td style="width: 25%;">true, false</td>
  <td style="width: 25%;">True</td>
  <td style="width: 25%;">false</td>
 </tr>
 <tr>
  <td style="width: 25%;">filter_rel_int_range_min</td>
  <td style="width: 25%;">0.0-1.0</td>
  <td style="width: 25%;">False</td>
  <td style="width: 25%;">0.0</td>
 </tr>
 <tr>
  <td style="width: 25%;">filter_rel_int_range_max</td>
  <td style="width: 25%;">0.0-1.0</td>
  <td style="width: 25%;">False</td>
  <td style="width: 25%;">1.0</td>
 </tr>
 <tr>
  <td style="width: 25%;">filter_rel_area_range_min</td>
  <td style="width: 25%;">0.0-1.0</td>
  <td style="width: 25%;">False</td>
  <td style="width: 25%;">0.0</td>
 </tr>
 <tr>
  <td style="width: 25%;">filter_rel_area_range_max</td>
  <td style="width: 25%;">0.0-1.0</td>
  <td style="width: 25%;">False</td>
  <td style="width: 25%;">1.0</td>
 </tr>
</table>

### [`blank_assignment` (optional)](../modules/metadata.blank.md)

<table style="width: 100%;">
 <tr>
  <td style="width: 25%;"><b>Key</b></td>
  <td style="width: 25%;"><b>Possible Values</b></td>
  <td style="width: 25%;"><b>Required</b></td>
  <td style="width: 25%;"><b>Default</b></td>
 </tr>
 <tr>
  <td style="width: 25%;">activate_module</td>
  <td style="width: 25%;">true, false</td>
  <td style="width: 25%;">True</td>
  <td style="width: 25%;">false</td>
 </tr>
 <tr>
  <td style="width: 25%;">factor</td>
  <td style="width: 25%;">>=1</td>
  <td style="width: 25%;">False</td>
  <td style="width: 25%;">10</td>
 </tr>
 <tr>
  <td style="width: 25%;">algorithm</td>
  <td style="width: 25%;">mean, median, maximum</td>
  <td style="width: 25%;">False</td>
  <td style="width: 25%;">mean</td>
 </tr>
 <tr>
  <td style="width: 25%;">value</td>
  <td style="width: 25%;">height, area</td>
  <td style="width: 25%;">False</td>
  <td style="width: 25%;">area</td>
 </tr>
</table>

### [`group_factor_assignment` (optional)](../modules/metadata.group_fold.md)

<table style="width: 100%;">
 <tr>
  <td style="width: 25%;"><b>Key</b></td>
  <td style="width: 25%;"><b>Possible Values</b></td>
  <td style="width: 25%;"><b>Required</b></td>
  <td style="width: 25%;"><b>Default</b></td>
 </tr>
 <tr>
  <td style="width: 25%;">activate_module</td>
  <td style="width: 25%;">true, false</td>
  <td style="width: 25%;">True</td>
  <td style="width: 25%;">false</td>
 </tr>
 <tr>
  <td style="width: 25%;">algorithm</td>
  <td style="width: 25%;">mean, median, maximum</td>
  <td style="width: 25%;">False</td>
  <td style="width: 25%;">mean</td>
 </tr>
 <tr>
  <td style="width: 25%;">value</td>
  <td style="width: 25%;">height, area</td>
  <td style="width: 25%;">False</td>
  <td style="width: 25%;">area</td>
 </tr>
</table>

### `phenotype_assignment` (optional)

#### [`qualitative` (optional)](../modules/phenotype.qualitative.md)

<table style="width: 100%;">
 <tr>
  <td style="width: 25%;"><b>Key</b></td>
  <td style="width: 25%;"><b>Possible Values</b></td>
  <td style="width: 25%;"><b>Required</b></td>
  <td style="width: 25%;"><b>Default</b></td>
 </tr>
 <tr>
  <td style="width: 25%;">activate_module</td>
  <td style="width: 25%;">true, false</td>
  <td style="width: 25%;">True</td>
  <td style="width: 25%;">false</td>
 </tr>
 <tr>
  <td style="width: 25%;">factor</td>
  <td style="width: 25%;">>=1</td>
  <td style="width: 25%;">False</td>
  <td style="width: 25%;">10</td>
 </tr>
 <tr>
  <td style="width: 25%;">algorithm</td>
  <td style="width: 25%;">minmax, median, mean</td>
  <td style="width: 25%;">False</td>
  <td style="width: 25%;">minmax</td>
 </tr>
 <tr>
  <td style="width: 25%;">value</td>
  <td style="width: 25%;">height, area</td>
  <td style="width: 25%;">False</td>
  <td style="width: 25%;">area</td>
 </tr>
</table>

#### [`quantitative-percentage` (optional)](../modules/phenotype.quant-percent.md)

<table style="width: 100%;">
 <tr>
  <td style="width: 25%;"><b>Key</b></td>
  <td style="width: 25%;"><b>Possible Values</b></td>
  <td style="width: 25%;"><b>Required</b></td>
  <td style="width: 25%;"><b>Default</b></td>
 </tr>
 <tr>
  <td style="width: 25%;">activate_module</td>
  <td style="width: 25%;">true, false</td>
  <td style="width: 25%;">True</td>
  <td style="width: 25%;">false</td>
 </tr>
 <tr>
  <td style="width: 25%;">sample_avg</td>
  <td style="width: 25%;">mean, median</td>
  <td style="width: 25%;">False</td>
  <td style="width: 25%;">mean</td>
 </tr>
 <tr>
  <td style="width: 25%;">value</td>
  <td style="width: 25%;">area</td>
  <td style="width: 25%;">False</td>
  <td style="width: 25%;">area</td>
 </tr>
 <tr>
  <td style="width: 25%;">algorithm</td>
  <td style="width: 25%;">pearson</td>
  <td style="width: 25%;">False</td>
  <td style="width: 25%;">pearson</td>
 </tr>
 <tr>
  <td style="width: 25%;">p_val_cutoff</td>
  <td style="width: 25%;">0.0-1.0</td>
  <td style="width: 25%;">False</td>
  <td style="width: 25%;">0.05</td>
 </tr>
 <tr>
  <td style="width: 25%;">coeff_cutoff</td>
  <td style="width: 25%;">0.0-1.0</td>
  <td style="width: 25%;">False</td>
  <td style="width: 25%;">0.7</td>
 </tr>
</table>

#### [`quantitative-concentration` (optional)](../modules/phenotype.quant-concentr.md)

<table style="width: 100%;">
 <tr>
  <td style="width: 25%;"><b>Key</b></td>
  <td style="width: 25%;"><b>Possible Values</b></td>
  <td style="width: 25%;"><b>Required</b></td>
  <td style="width: 25%;"><b>Default</b></td>
 </tr>
 <tr>
  <td style="width: 25%;">activate_module</td>
  <td style="width: 25%;">true, false</td>
  <td style="width: 25%;">True</td>
  <td style="width: 25%;">false</td>
 </tr>
 <tr>
  <td style="width: 25%;">sample_avg</td>
  <td style="width: 25%;">mean, median</td>
  <td style="width: 25%;">False</td>
  <td style="width: 25%;">mean</td>
 </tr>
 <tr>
  <td style="width: 25%;">value</td>
  <td style="width: 25%;">area</td>
  <td style="width: 25%;">False</td>
  <td style="width: 25%;">area</td>
 </tr>
 <tr>
  <td style="width: 25%;">algorithm</td>
  <td style="width: 25%;">pearson</td>
  <td style="width: 25%;">False</td>
  <td style="width: 25%;">pearson</td>
 </tr>
 <tr>
  <td style="width: 25%;">p_val_cutoff</td>
  <td style="width: 25%;">0.0-1.0</td>
  <td style="width: 25%;">False</td>
  <td style="width: 25%;">0.05</td>
 </tr>
 <tr>
  <td style="width: 25%;">coeff_cutoff</td>
  <td style="width: 25%;">0.0-1.0</td>
  <td style="width: 25%;">False</td>
  <td style="width: 25%;">0.7</td>
 </tr>
</table>

### [`spectral_library_matching` (optional)](../modules/annotation.userlib.md)

#### `modified_cosine` (optional)

<table style="width: 100%;">
 <tr>
  <td style="width: 25%;"><b>Key</b></td>
  <td style="width: 25%;"><b>Possible Values</b></td>
  <td style="width: 25%;"><b>Required</b></td>
  <td style="width: 25%;"><b>Default</b></td>
 </tr>
 <tr>
  <td style="width: 25%;">activate_module</td>
  <td style="width: 25%;">true, false</td>
  <td style="width: 25%;">True</td>
  <td style="width: 25%;">false</td>
 </tr>
 <tr>
  <td style="width: 25%;">min_nr_matched_peaks</td>
  <td style="width: 25%;"> >=1 </td>
  <td style="width: 25%;">False</td>
  <td style="width: 25%;">5</td>
 </tr>
 <tr>
  <td style="width: 25%;">fragment_tol</td>
  <td style="width: 25%;"> >0 </td>
  <td style="width: 25%;">False</td>
  <td style="width: 25%;">0.1</td>
 </tr>
 <tr>
  <td style="width: 25%;">score_cutoff</td>
  <td style="width: 25%;">0.0-1.0</td>
  <td style="width: 25%;">False</td>
  <td style="width: 25%;">0.7</td>
 </tr>
 <tr>
  <td style="width: 25%;">max_precursor_mass_diff</td>
  <td style="width: 25%;"> >=1 </td>
  <td style="width: 25%;">False</td>
  <td style="width: 25%;">600</td>
 </tr>
 <tr>
  <td style="width: 25%;">maximum_runtime</td>
  <td style="width: 25%;"> >=0 </td>
  <td style="width: 25%;">False</td>
  <td style="width: 25%;">0 (unlimited)</td>
 </tr>
</table>

#### `ms2deepscore` (optional)

<table style="width: 100%;">
 <tr>
  <td style="width: 25%;"><b>Key</b></td>
  <td style="width: 25%;"><b>Possible Values</b></td>
  <td style="width: 25%;"><b>Required</b></td>
  <td style="width: 25%;"><b>Default</b></td>
 </tr>
 <tr>
  <td style="width: 25%;">activate_module</td>
  <td style="width: 25%;">true, false</td>
  <td style="width: 25%;">True</td>
  <td style="width: 25%;">false</td>
 </tr>
 <tr>
  <td style="width: 25%;">score_cutoff</td>
  <td style="width: 25%;">0.0-1.0</td>
  <td style="width: 25%;">False</td>
  <td style="width: 25%;">0.8</td>
 </tr>
 <tr>
  <td style="width: 25%;">max_precursor_mass_diff</td>
  <td style="width: 25%;"> >=1 </td>
  <td style="width: 25%;">False</td>
  <td style="width: 25%;">600</td>
 </tr>
 <tr>
  <td style="width: 25%;">maximum_runtime</td>
  <td style="width: 25%;"> >=0 </td>
  <td style="width: 25%;">False</td>
  <td style="width: 25%;">0 (unlimited)</td>
 </tr>
</table>

### [`as_kcb_matching` (optional)](../modules/annotation.as_kcb.md)

#### `modified_cosine` (optional)

<table style="width: 100%;">
 <tr>
  <td style="width: 25%;"><b>Key</b></td>
  <td style="width: 25%;"><b>Possible Values</b></td>
  <td style="width: 25%;"><b>Required</b></td>
  <td style="width: 25%;"><b>Default</b></td>
 </tr>
 <tr>
  <td style="width: 25%;">activate_module</td>
  <td style="width: 25%;">true, false</td>
  <td style="width: 25%;">True</td>
  <td style="width: 25%;">false</td>
 </tr>
 <tr>
  <td style="width: 25%;">min_nr_matched_peaks</td>
  <td style="width: 25%;"> >=1 </td>
  <td style="width: 25%;">False</td>
  <td style="width: 25%;">5</td>
 </tr>
 <tr>
  <td style="width: 25%;">fragment_tol</td>
  <td style="width: 25%;"> >0 </td>
  <td style="width: 25%;">False</td>
  <td style="width: 25%;">0.1</td>
 </tr>
 <tr>
  <td style="width: 25%;">score_cutoff</td>
  <td style="width: 25%;">0.0-1.0</td>
  <td style="width: 25%;">False</td>
  <td style="width: 25%;">0.5</td>
 </tr>
 <tr>
  <td style="width: 25%;">max_precursor_mass_diff</td>
  <td style="width: 25%;"> >=1 </td>
  <td style="width: 25%;">False</td>
  <td style="width: 25%;">600</td>
 </tr>
 <tr>
  <td style="width: 25%;">maximum_runtime</td>
  <td style="width: 25%;"> >=0 </td>
  <td style="width: 25%;">False</td>
  <td style="width: 25%;">0 (unlimited)</td>
 </tr>
</table>

#### `ms2deepscore` (optional)

<table style="width: 100%;">
 <tr>
  <td style="width: 25%;"><b>Key</b></td>
  <td style="width: 25%;"><b>Possible Values</b></td>
  <td style="width: 25%;"><b>Required</b></td>
  <td style="width: 25%;"><b>Default</b></td>
 </tr>
 <tr>
  <td style="width: 25%;">activate_module</td>
  <td style="width: 25%;">true, false</td>
  <td style="width: 25%;">True</td>
  <td style="width: 25%;">false</td>
 </tr>
 <tr>
  <td style="width: 25%;">score_cutoff</td>
  <td style="width: 25%;">0.0-1.0</td>
  <td style="width: 25%;">False</td>
  <td style="width: 25%;">0.7</td>
 </tr>
 <tr>
  <td style="width: 25%;">max_precursor_mass_diff</td>
  <td style="width: 25%;"> >=1 </td>
  <td style="width: 25%;">False</td>
  <td style="width: 25%;">600</td>
 </tr>
 <tr>
  <td style="width: 25%;">maximum_runtime</td>
  <td style="width: 25%;"> >=0 </td>
  <td style="width: 25%;">False</td>
  <td style="width: 25%;">0 (unlimited)</td>
 </tr>
</table>