## Context
This repository was forked from the original scib-metrics project (YosefLab/scib-metrics) but needs to establish its own identity as scDCB-metrics. The current codebase still contains references to the original project's branding, metadata, and infrastructure.

## Goals / Non-Goals
### Goals:
- Establish clear identity for scDCB-metrics project
- Update all package metadata and references
- Maintain functional compatibility with original API
- Update CI/CD for new repository
- Ensure proper attribution while distinguishing from original

### Non-Goals:
- Change core functionality or algorithms
- Modify API signatures (except import paths)
- Change dependency requirements
- Alter test behavior or expected results

## Decisions
### Decision: Complete rename rather than aliasing
We will perform a complete rename from `scib-metrics` to `scdcb-metrics` rather than maintaining backward compatibility aliases. This ensures clear distinction and avoids confusion between the two projects.

**Alternatives considered:**
1. **Maintain `scib-metrics` name with different metadata** - Rejected: Causes confusion and potential package conflicts
2. **Create compatibility layer/aliases** - Rejected: Adds complexity and maintenance burden
3. **Gradual migration with deprecation warnings** - Rejected: Not necessary for a clean fork

### Decision: Preserve directory structure
We will rename the source directory but preserve the internal module structure to minimize disruption.

**Alternatives considered:**
1. **Restructure modules** - Rejected: Unnecessary for a branding change
2. **Flatten hierarchy** - Rejected: Would break existing import patterns

### Decision: Update all references comprehensively
We will update all references including documentation, tests, and configuration files to ensure consistency.

## Risks / Trade-offs
- **Risk**: Breaking existing user code that imports `scib_metrics`
  - **Mitigation**: Clear communication about the change, version bump, and migration instructions
- **Risk**: CI/CD integration issues
  - **Mitigation**: Test workflows thoroughly before and after changes
- **Risk**: Documentation links breaking
  - **Mitigation**: Update all documentation references and consider redirects if possible

## Migration Plan
1. Update package metadata and source structure
2. Update documentation and configuration
3. Update CI/CD workflows
4. Test thoroughly
5. Release as new major version
6. Communicate change to users

## Open Questions
- Should we maintain any reference to the original scib-metrics project in documentation?
- Are there any external integrations that need to be updated (e.g., ReadTheDocs, PyPI)?