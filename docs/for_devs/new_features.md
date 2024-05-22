This is a short step-by-step guide on how to add new functionality:

- Modify the params.json and the schema.json files to add the parameters of the new class and their descriptions. Do not hardcode values. Respect the different categories: `files`, `core_modules` (run by default), `additional_modules` (do not run by default).
- Add an input handling class, add validation methods, and implement it into the ParameterManger. Write appropriate tests.
- If data parsing is performed, add the appropriate parser to GeneralParser. Write appropriate tests and provide example files.
- Add an appropriate analysis class and implement it into the AnalysisManager class. Write appropriate tests.
- Implement the appropriate export methods in the ExportManager (to json, csv, or summary). Write appropriate tests.
- Increment the version in pyproject.toml
- Update the online documentation with a description of the module, its algorithm, the parameters, and the limitations.
- Implement the appropriate input forms into fermo_gui to run your module.
- Implement appropriate search/filtering options to search for your results on fermo_gui.
