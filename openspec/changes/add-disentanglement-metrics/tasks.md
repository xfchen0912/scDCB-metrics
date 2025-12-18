## 1. Module Structure Setup
- [ ] 1.1 Create `src/scdice_metrics/metrics/disentanglement/` directory
- [ ] 1.2 Create `src/scdice_metrics/metrics/disentanglement/__init__.py` with proper exports
- [ ] 1.3 Update `src/scdice_metrics/metrics/__init__.py` to include disentanglement metrics in `__all__`
- [ ] 1.4 Create base utility functions in `src/scdice_metrics/metrics/disentanglement/_utils.py`

## 2. MIG (Mutual Information Gap) Implementation
- [ ] 2.1 Create `src/scdice_metrics/metrics/disentanglement/_mig.py` with MIG implementation
- [ ] 2.2 Implement mutual information estimation using JAX where applicable
- [ ] 2.3 Add batch processing support and input validation
- [ ] 2.4 Write comprehensive docstrings with examples
- [ ] 2.5 Add to `src/scdice_metrics/metrics/disentanglement/__init__.py` exports

## 3. DCI (Disentanglement, Completeness, Informativeness) Implementation
- [ ] 3.1 Create `src/scdice_metrics/metrics/disentanglement/_dci.py` with DCI implementation
- [ ] 3.2 Implement all three components: disentanglement, completeness, informativeness
- [ ] 3.3 Add support for computing individual components separately
- [ ] 3.4 Write comprehensive docstrings with examples
- [ ] 3.5 Add to `src/scdice_metrics/metrics/disentanglement/__init__.py` exports

## 4. SAP (Separated Attribute Predictability) Implementation
- [ ] 4.1 Create `src/scdice_metrics/metrics/disentanglement/_sap.py` with SAP implementation
- [ ] 4.2 Implement linear regression-based predictability scoring
- [ ] 4.3 Add configuration options for regression parameters
- [ ] 4.4 Write comprehensive docstrings with examples
- [ ] 4.5 Add to `src/scdice_metrics/metrics/disentanglement/__init__.py` exports

## 5. Entropy Utility Functions Implementation
- [ ] 5.1 Create `src/scdice_metrics/utils/_entropy.py` with entropy and mutual information functions
- [ ] 5.2 Implement Shannon entropy calculation with JAX acceleration
- [ ] 5.3 Implement mutual information estimation for continuous and discrete variables
- [ ] 5.4 Add batch processing support for entropy calculations
- [ ] 5.5 Write comprehensive docstrings with examples
- [ ] 5.6 Update `src/scdice_metrics/utils/__init__.py` to export entropy functions

## 6. JAX Acceleration Integration
- [ ] 6.1 Review existing JAX patterns in `src/scdice_metrics/nearest_neighbors/_jax.py`
- [ ] 6.2 Apply similar JAX acceleration patterns to disentanglement metrics where applicable
- [ ] 6.3 Implement fallback to NumPy/SciPy when JAX is not available
- [ ] 6.4 Add appropriate warnings for fallback mode

## 7. Benchmarker Integration
- [ ] 7.1 Update `src/scdice_metrics/benchmark/__init__.py` to include disentanglement metrics
- [ ] 7.2 Modify `src/scdice_metrics/benchmark/_core.py` to support disentanglement metric evaluation
- [ ] 7.3 Ensure consistent configuration patterns with existing metrics
- [ ] 7.4 Update benchmarker documentation with disentanglement metric examples

## 8. Documentation and Examples
- [ ] 8.1 Update `src/scdice_metrics/__init__.py` docstring to mention disentanglement metrics
- [ ] 8.2 Create example usage in docstrings for each metric
- [ ] 8.3 Update README.md to include disentanglement metrics section
- [ ] 8.4 Add basic usage examples in documentation