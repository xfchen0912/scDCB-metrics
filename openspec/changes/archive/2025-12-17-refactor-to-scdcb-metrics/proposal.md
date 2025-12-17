# Change: Refactor infrastructure from scib-metrics to scDCB-metrics

## Why
This repository is a fork of the original scib-metrics project but needs to establish its own identity as scDCB-metrics. The current infrastructure still references the original project's branding, URLs, and metadata, which creates confusion and prevents proper attribution.

## What Changes
- **BREAKING**: Rename Python package from `scib-metrics` to `scdcb-metrics`
- Update all package metadata (name, description, URLs, author information)
- Update documentation references and badges
- Update CI/CD configuration for new repository
- Update import statements and module structure
- Update test configurations and references

## Impact
- Affected specs: package-identity, ci-cd, documentation
- Affected code: pyproject.toml, README.md, all Python modules, GitHub Actions workflows, documentation files
- Users will need to install via `pip install scdcb-metrics` instead of `scib-metrics`
- Import statements will change from `import scib_metrics` to `import scdcb_metrics`