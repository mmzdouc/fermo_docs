## Overall organization

`fermo_core` can be categorized into three parts:

- **Data input/output**: parses and assigns input and output parameters, performs data input validations, manages export
- **Data processing**: parses input files, creates objects to hold feature and sample information
- **Data analysis**: performs individual analysis steps, such as annotation and filtering.

## Design patterns

`fermo_core` follows design patterns where appropriate and extensively uses the manager design pattern: a class that is responsible for managing and  calling in other classes with similar functionality. The most important manager classes are:

- **ParameterManager**: manages classes containing (input) parameters.
- **GeneralParser**: manages all file parser classes
- **AnalysisManager**: manages all data analysis and annotation classes
- **ExportManager**: manages data export classes

## Data storage

Data storage in `fermo_core` is concentrated in a few centralized classes which are modified by all other classes. The only exception is the ParameterManager, which stores parameters, but is never modified (except by initial user data input). The data storage classes are:

- The **Stats** class, which stores overall and general information. Only a single Stats object is instantiated per analysis run.
- The **Feature** class, which stores feature-related data. Is instantiated either as “General feature” (stores general information) or “Sample-specific” feature (storing sample-specific information. Instances of the Feature class are always stored in a Repository (following the repository design pattern)
- The **Sample** class, which stores sample-specific information. Instances of the Sample class are always stored in a Repository (following the repository design pattern).
