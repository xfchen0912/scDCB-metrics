# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

scDCB-metrics is a Python package providing accelerated, Python-only metrics for benchmarking single-cell integration outputs. It is a fork of scib-metrics with modifications for specific benchmarking needs. The package implements metrics from the scIB manuscript using JAX for jit-compilation and hardware acceleration.

## Development Commands

### Installation & Setup
```bash
# Install in development mode with all dependencies
pip install -e ".[dev,test]"

# For GPU acceleration, install appropriate JAX version separately
# See: https://github.com/google/jax#installation
```

### Testing
```bash
# Run all tests with coverage
coverage run -m pytest -v

# Run specific test file
pytest tests/test_metrics.py -v

# Run tests for specific module
pytest tests/test_metrics.py::test_silhouette_label -v

# Generate coverage report
coverage report
```

### Linting & Formatting
```bash
# Format code with ruff
ruff format src/ tests/

# Check linting with ruff
ruff check src/ tests/

# Auto-fix linting issues
ruff check --fix src/ tests/
```

### Building & Distribution
```bash
# Build package
python -m build

# Check package
twine check --strict dist/*.whl
```

### Documentation
```bash
# Build documentation (requires doc dependencies)
cd docs && make html
```

## Architecture

### Core Structure
- `src/scib_metrics/` - Main package source
  - `metrics/` - Individual metric implementations (graph_connectivity, isolated_labels, kbet, lisi, nmi_ari, pcr_comparison, silhouette)
  - `nearest_neighbors/` - Nearest neighbor algorithms with JAX and PyNNDescent backends
  - `utils/` - Utility functions (PCA, PCR, silhouette, distance calculations, etc.)
  - `benchmark/` - Benchmarker classes for batch correction and biological conservation evaluation
  - `_settings.py` - Package settings and configuration
  - `_types.py` - Type definitions

### Key Design Patterns
1. **JAX Acceleration**: Metrics use JAX for jit-compilation when possible. Check `nearest_neighbors/_jax.py` for JAX-based implementations.
2. **Backend Abstraction**: Nearest neighbor algorithms have multiple backends (JAX, PyNNDescent) with a common interface.
3. **Benchmarker Classes**: `Benchmarker`, `BioConservation`, and `BatchCorrection` provide high-level evaluation interfaces.
4. **Type Safety**: Extensive use of type hints throughout the codebase.

### Important Dependencies
- **JAX/jaxlib**: For accelerated computations
- **anndata/scanpy**: Single-cell data structures
- **scikit-learn**: Machine learning utilities
- **pynndescent**: Approximate nearest neighbors
- **igraph**: Graph algorithms

## Testing Strategy

Tests are organized in `tests/` with:
- `test_metrics.py` - Individual metric tests
- `test_benchmarker.py` - Benchmarker class tests
- `test_neighbors.py` - Nearest neighbor algorithm tests
- `test_pcr_comparison.py` - PCR comparison tests
- `utils/` - Test utilities and data generation

Tests use `pytest` with coverage reporting. Environment variable `MPLBACKEND=agg` is set for headless matplotlib.

## OpenSpec Integration

This project uses OpenSpec for spec-driven development. Always check `openspec/AGENTS.md` when:
- Planning new features or architectural changes
- Making breaking changes
- Working on performance/security improvements

The OpenSpec workflow involves creating proposals in `openspec/changes/` with `proposal.md`, `tasks.md`, and spec deltas before implementation.

## Code Conventions

- **Line length**: 120 characters (configured in ruff)
- **Imports**: Use `ruff` for import sorting with specific conventions
- **Docstrings**: NumPy style (configured in ruff)
- **Type hints**: Required for all functions
- **Error handling**: Use specific exceptions with clear messages

## Common Development Tasks

1. **Adding a new metric**: Implement in `src/scib_metrics/metrics/`, add to `__init__.py`, write tests in `tests/test_metrics.py`.
2. **Modifying existing metric**: Update implementation, ensure backward compatibility, update tests.
3. **Performance optimization**: Use JAX jit compilation, profile with appropriate tools.
4. **Documentation updates**: Update docstrings, rebuild docs with `make html` in `docs/`.

## Environment Notes

- Python 3.10+ required (3.13 supported)
- JAX installation may require platform-specific steps for GPU support
- Pre-commit hooks are configured for code quality
- GitHub Actions run tests on Linux, macOS, and Windows
