# Change: Implement Disentanglement Metrics with modular structure

## Why
The scDICE-metrics package currently lacks dedicated metrics for evaluating disentanglement in single-cell models. Disentanglement metrics are crucial for assessing how well latent representations separate biological factors of variation. Adding these metrics will enhance the package's value for evaluating causal and disentangled representations in single-cell data.

## What Changes
- Add new `disentanglement/` subpackage under `src/scdice_metrics/metrics/` with modular structure
- Implement core disentanglement metrics: MIG (Mutual Information Gap), DCI (Disentanglement, Completeness, Informativeness), and SAP (Separated Attribute Predictability)
- Add entropy utility functions in `src/scdice_metrics/utils/_entropy.py` to support information-theoretic calculations
- Create JAX-accelerated implementations where applicable for performance
- Add integration with existing benchmarker classes for consistent evaluation
- Provide comprehensive documentation and examples for using disentanglement metrics

## Impact
- Affected specs: disentanglement-metrics, metrics-module
- Affected code: `src/scdice_metrics/metrics/` directory structure, benchmarker classes, documentation
- Key systems: Metric computation, JAX acceleration, benchmarking framework