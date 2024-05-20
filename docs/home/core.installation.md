`fermo_core` is a Python-based command line tool. While primarily intended to be the backend processing module of `fermo_gui` of the application FERMO, `fermo_core` can be used independently for large-scale data processing and analysis.

**Nota Bene**: `fermo_core` is intended to run on Linux and has only been tested on Ubuntu Linux. No support for other operating systems is planned.

## Installation

### With `hatch`
- Install `python 3.11.x`
- Install hatch (e.g. with `pipx install hatch`)
- Download or clone the `fermo_core` [repository](https://github.com/mmzdouc/fermo_core)
- (Change into the fermo_core base directory if not already present)
- Run `hatch -v env create`
- Once installed, run as specified in Usage

### With `conda`
- Download or clone this repository
- Install conda
- Create a conda environment with `conda create --name fermo_core python=3.11`
- Activate the conda environment with `conda activate fermo_core`
- Download or clone the `fermo_core` [repository](https://github.com/mmzdouc/fermo_core)
- (Change into the fermo_core base directory if not already present)
- Run `pip install -e .`
- Once installed, run as specified in Usage
