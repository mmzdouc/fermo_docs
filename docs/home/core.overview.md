## Overview `fermo_core`

*FERMO* consists of two parts:

- `fermo_gui`: the dashboard graphical user interface. 
- `fermo_core`: the data processing and analysis pipeline (the backend).

This part of the documentation describes `fermo_core` in more detail.

### Who is `fermo_core` for? 

While `fermo_core` is primarily intended to be the data processing backend of `fermo_gui`, it can also be used as a command line application. 

*Nota bene*: `fermo_core` is not very beginner-friendly, and requires some experience with command line tools. For a more user-friendly version, please see `fermo_gui`.

### Why use `fermo_core`?

As command line application, `fermo_core` can be used for large scale data analysis, design-of-experiment, and data processing automation. `fermo_core` does not come with its own data visualization, but the produced files can be either uploaded in the `fermo_gui` or used in downstream processing tools.
