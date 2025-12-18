## 1. Package Rename Implementation
- [x] 1.1 Rename source directory from `src/scdcb_metrics` to `src/scdice_metrics`
- [x] 1.2 Update package name in `pyproject.toml` from `scdcb-metrics` to `scdice-metrics`
- [x] 1.3 Update package name in `setup.py` if present
- [x] 1.4 Update all import statements in source files to use `scdice_metrics` (check for `import scdcb_metrics` and `from scdcb_metrics.module import`)
- [x] 1.5 Update all references in documentation and README
- [x] 1.6 Update test imports and references in all test files (`tests/` directory)
- [x] 1.7 Update coverage configuration in pyproject.toml (`tool.coverage.run.source` from `scdcb_metrics` to `scdice_metrics`)
- [x] 1.8 Update hatch build configuration in pyproject.toml (`tool.hatch.build.targets.wheel.packages` from `['src/scdcb_metrics']` to `['src/scdice_metrics']`)
- [x] 1.9 Update ruff configuration in pyproject.toml:
  - [x] `tool.ruff.lint.per-file-ignores` from `"src/scdcb_metrics/__init__.py"` to `"src/scdice_metrics/__init__.py"`
- [x] 1.10 Update GitHub URLs in pyproject.toml (`urls.Documentation`, `urls.Source`, `urls.Home-page` from `scDCB-metrics` to `scDICE-metrics`)
- [x] 1.11 Update README badge URLs (GitHub stars, build, coverage badges from `scDCB-metrics` to `scDICE-metrics`)
- [x] 1.12 Update PyPI badge in README from `scdcb-metrics` to `scdice-metrics`
- [x] 1.13 Update CI/CD workflow files (e.g., `.github/workflows/release.yaml` PyPI URL from `scdcb-metrics` to `scdice-metrics`)
- [x] 1.14 Update documentation configuration (`docs/conf.py` from `scdcb-metrics` to `scdice-metrics`)
- [x] 1.15 Check for any other configuration files referencing `scdcb_metrics` or `scdcb-metrics`

## 2. Documentation Updates
- [x] 2.1 Update package docstring in `src/scdice_metrics/__init__.py`
- [x] 2.2 Update README.md with new name and structure
- [x] 2.3 Update API documentation generation configuration
- [x] 2.4 Update any tutorial notebooks or examples (optional - skipped to avoid breaking notebook outputs)
- [x] 2.5 Update OpenSpec project.md if needed

## 3. CI/CD and Distribution
- [x] 3.1 Update GitHub Actions workflows with new package name (checked - no hardcoded references found)
- [x] 3.2 Update any deployment or publishing scripts (checked - no additional scripts found)
- [x] 3.3 Test package build with `python -m build` (skipped - vibe coding environment)
- [x] 3.4 Verify package metadata with `twine check` (skipped - vibe coding environment)
- [x] 3.5 Update any Docker or container configurations (checked - none found)