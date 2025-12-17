## ADDED Requirements
### Requirement: Package Identity
The package SHALL be named `scdice-metrics` (Python package name: `scdice_metrics`) to reflect its focus on disentanglement and causality evaluation in single-cell models.

#### Scenario: Package installation
- **WHEN** a user installs the package via `pip install scdice-metrics`
- **THEN** the package is installed with the correct name and can be imported as `import scdice_metrics`

#### Scenario: Development installation
- **WHEN** a developer installs the package in development mode
- **THEN** the source code is located at `src/scdice_metrics/` and all imports use `scdice_metrics`

#### Scenario: Package metadata
- **WHEN** inspecting package metadata
- **THEN** the name is `scdice-metrics`, version follows semantic versioning, and author information is correct

## MODIFIED Requirements
### Requirement: Package Configuration
The package configuration files SHALL reference the correct package name `scdice-metrics` and `scdice_metrics`.

#### Scenario: PyPI publication
- **WHEN** the package is built for distribution
- **THEN** `pyproject.toml` contains `name = "scdice-metrics"` and build configuration references `scdice_metrics`

#### Scenario: Test execution
- **WHEN** tests are run with pytest
- **THEN** test imports use `scdice_metrics` and coverage configuration tracks `scdice_metrics` source files

#### Scenario: Code quality checks
- **WHEN** linting and formatting tools are run
- **THEN** ruff configuration correctly identifies `src/scdice_metrics` as the source directory

## REMOVED Requirements
### Requirement: Old Package Identity
**Reason**: The package is being renamed from `scdcb-metrics` to better reflect its focus on disentanglement and causality.
**Migration**: All references to `scdcb-metrics` or `scdcb_metrics` should be updated to `scdice-metrics` or `scdice_metrics` respectively.