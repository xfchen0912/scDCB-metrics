# Change: Rename project to scDICE-metrics and setup modular structure

## Why
The project needs to be renamed from scDCB-metrics to scDICE-metrics to better reflect its focus on disentanglement and causality evaluation in single-cell models. Additionally, the current monolithic structure should be refactored into a more modular architecture to improve maintainability, enable selective imports, and support future extensions.

## What Changes
- **BREAKING**: Rename package from `scdcb_metrics` to `scdice_metrics` throughout the codebase
- **BREAKING**: Update package name in pyproject.toml, setup.py, and all configuration files
- **BREAKING**: Update import statements in all Python files, tests, and documentation
- Refactor source structure into modular subpackages for better organization
- Update documentation and README to reflect new name and structure
- Maintain backward compatibility where possible with deprecation warnings

## Impact
- Affected specs: package-identity, modular-architecture
- Affected code: All Python source files, configuration files, documentation, tests
- Key systems: Package installation, import system, CI/CD pipelines, documentation generation