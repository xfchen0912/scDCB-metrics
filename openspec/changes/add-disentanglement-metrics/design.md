## Context
The scDICE-metrics package currently provides metrics for single-cell integration benchmarking but lacks dedicated disentanglement metrics. Disentanglement evaluation is crucial for assessing how well latent representations separate biological factors of variation, which is particularly important for causal and disentangled representation learning in single-cell biology.

## Goals / Non-Goals
### Goals:
- Implement standard disentanglement metrics (MIG, DCI, SAP) with JAX acceleration
- Add entropy utility functions in `utils/_entropy.py` to support information-theoretic calculations
- Maintain consistency with existing package architecture and patterns
- Provide seamless integration with benchmarker classes
- Ensure performance through JAX jit-compilation where applicable

### Non-Goals:
- Implementing novel disentanglement metrics (focus on established standards)
- Creating visualization tools for disentanglement analysis
- Supporting real-time interactive evaluation
- Replacing existing metrics with disentanglement variants

## Decisions
### Decision: Modular Subpackage Structure
Disentanglement metrics will be implemented as a `disentanglement/` subpackage under `src/scdice_metrics/metrics/` to maintain consistency with the existing modular architecture.

**Alternatives considered:**
1. Adding disentanglement metrics as individual files in the main metrics directory (like `_mig.py`, `_dci.py`)
   - **Rejected**: Would clutter the main metrics directory and break the pattern of categorical organization
2. Creating a separate top-level package `scdice_metrics.disentanglement`
   - **Rejected**: Overly complex for metrics that are conceptually part of the metrics module

**Rationale**: The existing metrics module already uses individual files for different metric categories. A subpackage provides better organization for multiple related metrics while maintaining the established pattern.

### Decision: JAX Acceleration with Fallback
Disentanglement metrics will use JAX for acceleration where applicable, with fallback to NumPy/SciPy implementations when JAX is not available.

**Alternatives considered:**
1. JAX-only implementation
   - **Rejected**: Would limit usability for users without JAX installation
2. Pure NumPy/SciPy implementation
   - **Rejected**: Would miss performance benefits of JAX acceleration that aligns with package philosophy

**Rationale**: The package already uses JAX for acceleration in other components (e.g., nearest neighbors). Maintaining consistency while providing fallback ensures broad compatibility.

### Decision: Benchmarker Integration Pattern
Disentanglement metrics will integrate with existing benchmarker classes using the same pattern as other metrics, avoiding special-case handling.

**Alternatives considered:**
1. Separate disentanglement benchmarker class
   - **Rejected**: Would create inconsistency and require users to learn new interfaces
2. Modifying benchmarker base classes significantly
   - **Rejected**: Risk of breaking existing functionality

**Rationale**: Consistency with existing patterns reduces cognitive load for users and maintenance burden.

## Risks / Trade-offs
- **Performance overhead for fallback implementations** → Mitigation: Clear documentation of JAX benefits and installation instructions
- **Increased package dependencies** → Mitigation: Keep NumPy/SciPy as core dependencies, JAX as optional/extra
- **Complexity of multiple metric implementations** → Mitigation: Shared utility functions and consistent patterns across implementations

## Migration Plan
Not applicable - this is an additive feature that doesn't break existing functionality.

## Open Questions
- Should we include additional disentanglement metrics beyond the core three (MIG, DCI, SAP)?
- What are the optimal default parameters for each metric in single-cell contexts?
- How should we handle very high-dimensional latent spaces (common in single-cell models)?
- What additional information-theoretic utilities would be useful beyond basic entropy and mutual information?