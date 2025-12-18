## Context
The project is currently named scDCB-metrics with package name `scdcb_metrics`. It has a structure inherited from scib-metrics with modules organized under `metrics/`, `nearest_neighbors/`, `utils/`, and `benchmark/`. The project needs to be renamed to scDICE-metrics to better reflect its focus on disentanglement and causality evaluation. Additionally, the structure should be made more modular to improve maintainability and enable selective imports.

## Goals / Non-Goals

### Goals
1. Rename package from `scdcb_metrics` to `scdice_metrics` throughout the codebase
2. Update all configuration files, documentation, and references
3. Refactor into a modular structure with clear separation of concerns
4. Maintain backward compatibility where possible with deprecation warnings
5. Ensure all existing functionality and tests continue to work

### Non-Goals
1. Changing the core metric algorithms or their behavior
2. Adding new metrics or features (scope limited to rename and restructuring)
3. Changing external dependencies or Python version requirements
4. Modifying the API beyond what's necessary for the rename

## Decisions

### Decision 1: Preserve Existing Modular Structure
**What**: Maintain the existing modular package structure during the rename:
- `scdice_metrics.metrics` - Individual metric implementations (renamed from `scdcb_metrics.metrics`)
- `scdice_metrics.nearest_neighbors` - Nearest neighbor algorithms (renamed from `scdcb_metrics.nearest_neighbors`)
- `scdice_metrics.utils` - Utility functions (renamed from `scdcb_metrics.utils`)
- `scdice_metrics.benchmark` - Benchmarker classes (renamed from `scdcb_metrics.benchmark`)
- `scdice_metrics._settings` and `scdice_metrics._types` - Core settings and types

**Why**: 
- The existing modular structure already provides clear separation of concerns
- Maintains selective import capability (e.g., `from scdice_metrics.metrics import silhouette_label`)
- Minimizes disruption to the codebase architecture
- Preserves existing import patterns and dependencies

**Alternatives considered**:
- Reorganize structure: Would add unnecessary complexity to the rename operation
- Flatten structure: Would lose the benefits of modular organization

### Decision 2: Top-Level API Preservation
**What**: Maintain the existing top-level API through `scdice_metrics/__init__.py` imports

**Why**:
- Minimizes breaking changes for existing users
- Allows gradual migration to new import paths
- Maintains compatibility with existing code and documentation

**Alternatives considered**:
- Force users to use new import paths: More breaking but cleaner long-term
- Deprecation warnings: Chosen approach to guide users while maintaining compatibility

### Decision 3: Rename Strategy
**What**: Use systematic find-and-replace for all occurrences of `scdcb` to `scdice`

**Why**:
- Consistent naming throughout the codebase
- Avoids confusion between old and new names
- Simpler than maintaining aliases or compatibility layers

**Alternatives considered**:
- Maintain aliases: Adds complexity and maintenance burden
- Gradual migration: More complex to implement and test

## Risks / Trade-offs

### Risk: Breaking Changes
**Mitigation**: 
- Maintain backward compatibility through top-level imports
- Add deprecation warnings for old import paths
- Thorough testing of all existing functionality
- Clear migration documentation

### Risk: Import Path Confusion
**Mitigation**:
- Clear documentation of new import structure
- Examples showing both old and new import styles
- Deprecation warnings with guidance

### Risk: CI/CD Pipeline Breakage
**Mitigation**:
- Update all CI/CD configuration files
- Test package build and distribution
- Update coverage and testing configurations

## Migration Plan

1. **Phase 1: Source Rename**
   - Rename directory `src/scdcb_metrics` → `src/scdice_metrics`
   - Update all internal imports

2. **Phase 2: Configuration Updates**
   - Update pyproject.toml, setup.py, and other config files
   - Update CI/CD workflows

3. **Phase 3: Modular Restructuring**
   - Reorganize into subpackages
   - Update import statements
   - Update type hints and documentation

4. **Phase 4: Testing and Validation**
   - Run all existing tests
   - Verify package builds correctly
   - Test installation and basic usage

5. **Phase 5: Documentation Updates**
   - Update README and documentation
   - Update examples and tutorials
   - Add migration guide

## Open Questions
1. Should we maintain a compatibility module for a transition period?
2. Are there any external dependencies that reference the old package name?
3. Should we update the GitHub repository name as part of this change?