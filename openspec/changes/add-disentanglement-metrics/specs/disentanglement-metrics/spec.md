## ADDED Requirements
### Requirement: Disentanglement Metrics Module
The package SHALL provide a dedicated `disentanglement` submodule under `scdice_metrics.metrics` for evaluating disentanglement in single-cell model representations.

#### Scenario: Module structure
- **WHEN** examining the package structure
- **THEN** there is a `src/scdice_metrics/metrics/disentanglement/` directory containing disentanglement metric implementations

#### Scenario: Import availability
- **WHEN** importing from the metrics module
- **THEN** disentanglement metrics are available via `from scdice_metrics.metrics.disentanglement import mig, dci, sap`

### Requirement: Mutual Information Gap (MIG) Metric
The package SHALL implement the Mutual Information Gap (MIG) metric for evaluating disentanglement by measuring the gap in mutual information between each latent dimension and the ground truth factors.

#### Scenario: MIG computation
- **WHEN** computing MIG on latent representations with known ground truth factors
- **THEN** the metric returns a scalar value between 0 and 1 indicating disentanglement quality

#### Scenario: Batch processing support
- **WHEN** processing multiple samples or batches
- **THEN** the MIG implementation supports batched computation with JAX acceleration

### Requirement: DCI (Disentanglement, Completeness, Informativeness) Metric
The package SHALL implement the DCI metric which provides three separate scores: disentanglement, completeness, and informativeness for comprehensive evaluation.

#### Scenario: DCI computation
- **WHEN** computing DCI on latent representations
- **THEN** the metric returns three separate scores (disentanglement, completeness, informativeness) each between 0 and 1

#### Scenario: Component selection
- **WHEN** users only need specific components
- **THEN** they can compute individual DCI components (e.g., only disentanglement score) without computing all three

### Requirement: SAP (Separated Attribute Predictability) Metric
The package SHALL implement the SAP metric which measures how well individual latent dimensions can predict ground truth factors using linear regression.

#### Scenario: SAP computation
- **WHEN** computing SAP on latent representations
- **THEN** the metric returns a scalar value between 0 and 1 indicating attribute predictability

#### Scenario: Regression configuration
- **WHEN** configuring SAP computation
- **THEN** users can specify regression parameters and cross-validation settings

### Requirement: Entropy Utility Functions
The package SHALL provide entropy calculation utilities in `src/scdice_metrics/utils/_entropy.py` to support disentanglement metric computations.

#### Scenario: Entropy calculation availability
- **WHEN** computing information-theoretic metrics like MIG
- **THEN** entropy and mutual information functions are available from `scdice_metrics.utils._entropy`

#### Scenario: JAX-accelerated entropy
- **WHEN** JAX is available
- **THEN** entropy calculations use JAX acceleration for performance

#### Scenario: Batch processing support
- **WHEN** processing multiple samples
- **THEN** entropy functions support batched computation

### Requirement: JAX Acceleration
Disentanglement metrics SHALL leverage JAX for jit-compilation and hardware acceleration where applicable for performance.

#### Scenario: JAX backend usage
- **WHEN** computing disentanglement metrics on supported hardware
- **THEN** the implementations use JAX for accelerated computation

#### Scenario: Fallback support
- **WHEN** JAX is not available
- **THEN** metrics fall back to NumPy/SciPy implementations with appropriate warnings

### Requirement: Benchmarker Integration
Disentanglement metrics SHALL integrate with existing benchmarker classes (`Benchmarker`, `BioConservation`, `BatchCorrection`) for consistent evaluation.

#### Scenario: Benchmarker usage
- **WHEN** using the benchmarker classes
- **THEN** disentanglement metrics are available as evaluation options alongside existing metrics

#### Scenario: Configuration consistency
- **WHEN** configuring benchmark evaluations
- **THEN** disentanglement metrics use the same configuration patterns as existing metrics