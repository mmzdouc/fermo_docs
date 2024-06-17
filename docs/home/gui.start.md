# Usage

On the 'Start Analysis' page, new *FERMO* analysis jobs can be initiated.

Files can be uploaded using the individual upload fields. 

The analysis job can be started by clicking on the **'Start Analysis'** button at the bottom of the page.

The **only** file required is a **peaktable file** - all other files are optional.

While default parameters are provided, they need to be adjusted according to the **requirements of the data**.

*Nota bene: *FERMO* online versions employs some restrictions with regard to file size, computation time, and data storage to prevent excessive usage. Details can be found on the 'Start Analysis' page.*

#### Example

![full_run](../assets/images/screenshots/gui.start.full_run.gif){ width="60%" }

## Load parameters

This field allows to clone the parameter settings of a previous *FERMO* job (e.g. created by a colleague). 

To load the parameters, simply paste the *FERMO* job ID into the field, and click on the **'Load Job Parameters'** button.

*Nota bene: files and filenames are not retained and must be newly uploaded.*

#### Troubleshooting

If an old job ID does not exist anymore but you still want to clone the parameters, you can simply upload a previously created *FERMO* **session.json** file under [Load Session](./gui.load.md).
Take the newly generated *FERMO* job ID and use it to load the parameters.

#### Example

![load_params.png](../assets/images/screenshots/gui.load_params.gif){ width="60%" }

## Peaktable

The peaktable is the only file that is mandatory for analysis.

See [**here**](./input_output.md#molecular-feature-peaktable) for more information on the required peaktable format.

## MS/MS

*(optional)*

Availability of MS/MS data is very important for annotation tasks. If MS/MS data is available, it is highly recommended to include such a file in the analysis.
However, even if MS/MS data is provided, usually not all molecular features have associated MS/MS information, and *FERMO* will ignore such features in annotation tasks requiring MS/MS data.

See [**here**](./input_output.md#msms-spectrum-information) for more information on the required MS/MS file format.

By default, *FERMO* performs quality-filtering of MS/MS fragments. See [here](../modules/filter.msms.md) for additional information.

## Group Metadata

*(optional)*

Group Metadata allows to provide sample context information. 
Using sample grouping, the abundance of features across groups (area, intensity) can be compared. 
Additionally, sample blanks can be designated to identify background ions.

See [**here**](./input_output.md#group-metadata) for more information on the required Group Metadata file format.

## Phenotype Data

*(optional)*

Phenotype data allows to correlate feature abundance with a phenotype/bioactivity signal. 
*FERMO* supports three different data formats/strategies:

- 

add additional points
