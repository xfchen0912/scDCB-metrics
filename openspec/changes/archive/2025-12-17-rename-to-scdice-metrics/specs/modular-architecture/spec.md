## ADDED Requirements
### Requirement: Package Organization
The package SHALL maintain its existing modular structure during the rename from `scdcb_metrics` to `scdice_metrics`.

#### Scenario: Source code organization preservation
- **WHEN** examining the renamed source code
- **THEN** the modular structure is preserved with `metrics/`, `nearest_neighbors/`, `utils/`, and `benchmark/` subpackages under `scdice_metrics/`

#### Scenario: Import statement updates
- **WHEN** updating import statements during the rename
- **THEN** imports maintain the modular structure (e.g., `from scdice_metrics.metrics.graph_connectivity import graph_connectivity` instead of `from scdcb_metrics.metrics.graph_connectivity import graph_connectivity`)

#### Scenario: Selective imports continue to work
- **WHEN** a user wants to import only specific metrics after the rename
- **THEN** they can still use `from scdice_metrics.metrics import silhouette_label` as before

### Requirement: Backward Compatibility
The package SHALL maintain backward compatibility for existing users through top-level imports in `scdice_metrics/__init__.py`.

#### Scenario: Existing code continues to work
- **WHEN** existing code is updated to use the new package name
- **THEN** the code continues to work with the same import patterns

#### Scenario: Deprecation guidance
- **WHEN** users import from deprecated `scdcb_metrics` paths
- **THEN** they receive appropriate deprecation warnings with guidance on new import paths