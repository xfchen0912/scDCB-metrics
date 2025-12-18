## MODIFIED Requirements
### Requirement: Metrics Module Structure
The metrics module SHALL maintain a modular structure with organized subpackages for different metric categories, including a new `disentanglement` subpackage.

#### Scenario: Disentanglement subpackage addition
- **WHEN** examining the metrics module structure
- **THEN** there is a `disentanglement/` directory alongside existing metric categories like `_graph_connectivity.py`, `_silhouette.py`, etc.

#### Scenario: Import organization
- **WHEN** importing metrics
- **THEN** disentanglement metrics are organized under `scdice_metrics.metrics.disentanglement` while maintaining backward compatibility for existing imports

#### Scenario: __init__.py exports
- **WHEN** examining `src/scdice_metrics/metrics/__init__.py`
- **THEN** disentanglement metrics are exported alongside existing metrics in the `__all__` list