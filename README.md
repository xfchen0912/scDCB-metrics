# scDCB-metrics

[![Stars][badge-stars]][link-stars]
[![PyPI][badge-pypi]][link-pypi]
[![Build][badge-build]][link-build]
[![Coverage][badge-cov]][link-cov]

[badge-stars]: https://img.shields.io/github/stars/xfchen0912/scDCB-metrics?logo=GitHub&color=yellow
[link-stars]: https://github.com/xfchen0912/scDCB-metrics/stargazers
[badge-pypi]: https://img.shields.io/pypi/v/scdcb-metrics.svg
[link-pypi]: https://pypi.org/project/scdcb-metrics
[badge-build]: https://github.com/xfchen0912/scDCB-metrics/actions/workflows/build.yaml/badge.svg
[link-build]: https://github.com/xfchen0912/scDCB-metrics/actions/workflows/build.yaml/
[badge-cov]: https://codecov.io/gh/xfchen0912/scDCB-metrics/branch/main/graph/badge.svg
[link-cov]: https://codecov.io/gh/xfchen0912/scDCB-metrics

Accelerated and Python-only metrics for benchmarking single-cell integration outputs.

This package contains implementations of metrics for evaluating the performance of single-cell omics data integration methods. The implementations of these metrics use [JAX](https://jax.readthedocs.io/en/latest/) when possible for jit-compilation and hardware acceleration. All implementations are in Python.

This package is a fork of scib-metrics with modifications for specific benchmarking needs. Currently we are porting metrics used in the scIB [manuscript](https://www.nature.com/articles/s41592-021-01336-8) (and [code](https://github.com/theislab/scib)). Deviations from the original implementations are documented.

## Installation

You need to have Python 3.10 or newer installed on your system. If you don't have
Python installed, we recommend installing [Miniconda](https://docs.conda.io/en/latest/miniconda.html).

There are several options to install scDCB-metrics:

1. Install the latest release on PyPI:

```bash
pip install scdcb-metrics
```

2. Install the latest development version:

```bash
pip install git+https://github.com/xfchen0912/scDCB-metrics.git@main
```

To leverage hardware acceleration (e.g., GPU) please install the apprpriate version of [JAX](https://github.com/google/jax#installation) separately. Often this can be easier by using conda-distributed versions of JAX.

## Release notes

See the [changelog][changelog].

## Contact

For questions and help requests, you can reach out in the [scverse Discourse][link-discourse].
If you found a bug, please use the [issue tracker][issue-tracker].

## Citation

References for individual metrics can be found in the corresponding documentation. This package is heavily inspired by the single-cell integration benchmarking work:

```
@article{luecken2022benchmarking,
  title={Benchmarking atlas-level data integration in single-cell genomics},
  author={Luecken, Malte D and B{\"u}ttner, Maren and Chaichoompu, Kridsadakorn and Danese, Anna and Interlandi, Marta and M{\"u}ller, Michaela F and Strobl, Daniel C and Zappia, Luke and Dugas, Martin and Colom{\'e}-Tatch{\'e}, Maria and others},
  journal={Nature methods},
  volume={19},
  number={1},
  pages={41--50},
  year={2022},
  publisher={Nature Publishing Group}
}
```

[issue-tracker]: https://github.com/xfchen0912/scDCB-metrics/issues
