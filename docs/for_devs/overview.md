`fermo_core` is a Python data processing pipeline focusing on robust and reproducible analysis. It follows:

- modular, object-oriented programming
- test-driven development 
- clean code and good software craftsmanship principles
- good documentation and logging practices.

For more information on principles we follow and on how to contribute code, please consult [CONTRIBUTING](https://github.com/mmzdouc/fermo_core/blob/main/CONTRIBUTING.md).

## Getting started

- Install `python 3.11.x`
- Install hatch (e.g. with `pipx install hatch`)
- Clone the [repository](https://github.com/mmzdouc/fermo_core)
- (Change into the fermo_core base directory if not already present) 
- Install the package with developer dependencies `hatch -v env create dev`
- Install pre-commit with `hatch run dev:pre-commit install`
- Run test suite with `hatch run test:pytest --run_slow --run_high_cpu` - all test should pass
