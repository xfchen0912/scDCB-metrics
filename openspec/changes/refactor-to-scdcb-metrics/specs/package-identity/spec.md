## ADDED Requirements
### Requirement: scDCB-metrics Package Identity
The Python package SHALL be named `scdcb-metrics` and provide accelerated metrics for single-cell data integration benchmarking with a distinct identity from the original scib-metrics project.

#### Scenario: Package installation
- **WHEN** a user runs `pip install scdcb-metrics`
- **THEN** the package installs successfully with all dependencies
- **AND** the package metadata reflects scDCB-metrics branding

#### Scenario: Import usage
- **WHEN** a user imports the package in Python code
- **THEN** they use `import scdcb_metrics` or `from scdcb_metrics import ...`
- **AND** all module functions are accessible through the new namespace

## MODIFIED Requirements
### Requirement: Package Metadata
The package SHALL have metadata that identifies it as scDCB-metrics including:
- Package name: `scdcb-metrics`
- Description: Updated to reflect scDCB-metrics purpose
- Author/maintainer information: Updated to current maintainers
- URLs: Point to scDCB-metrics repository and documentation
- Version: Reset or continued from appropriate baseline

#### Scenario: Package inspection
- **WHEN** a user inspects package metadata via `pip show scdcb-metrics`
- **THEN** all fields reflect scDCB-metrics identity
- **AND** URLs point to the correct repository locations

#### Scenario: PyPI listing
- **WHEN** the package is published to PyPI
- **THEN** it appears as `scdcb-metrics` with correct metadata
- **AND** users can distinguish it from `scib-metrics`

## REMOVED Requirements
### Requirement: scib-metrics Package Identity
**Reason**: This repository is now scDCB-metrics, not scib-metrics
**Migration**: Users should install `scdcb-metrics` instead of `scib-metrics` and update import statements