# Time Series with HyP3 + MintPy

!!! note "Worked example coming"
    This page will have a worked NZ example notebook once one is available. For now, the links below are the best place to start.

---

This workflow uses **HyP3 multi-burst interferograms** (processed on demand through ASF) and **MintPy** for SBAS time series analysis. It is the recommended starting point for students — no SAR processing software required, and the pipeline runs in a Jupyter notebook.

---

## MintPy

[MintPy](https://mintpy.readthedocs.io/) (Miami InSAR Time-series software in Python) ingests HyP3 products directly and is well documented and actively maintained.

- [MintPy ReadTheDocs](https://mintpy.readthedocs.io/en/latest/)
- [HyP3 + MintPy demo notebook](https://mintpy.readthedocs.io/en/latest/demo_dataset/#sentinel-1_of_the_2019_ridgecrest_california_earthquake_sequence_with_hyp3) — 2019 Ridgecrest earthquake, same dataset as the ASF storyboards
- [MintPy tutorials on GitHub](https://github.com/insarlab/MintPy-tutorial)
- [OpenSARlab](https://opensarlab-docs.asf.alaska.edu/) — run MintPy in a cloud Jupyter environment with no local install
- [EarthScope 2025 short course notebooks](https://github.com/isceplus/2025-isceplus) — includes MintPy worked examples

**Key reference:** Yunjun, Z., Fattahi, H., & Amelung, F. (2019). Small baseline InSAR time series analysis: Unwrapping error correction and noise reduction. *Computers & Geosciences*, 133, 104331. [DOI](https://doi.org/10.1016/j.cageo.2019.104331)

---

## Acknowledgement

When using HyP3 products in reports, presentations, or publications:

> Hogenson, K., et al. (2020). *Hybrid Pluggable Processing Pipeline (HyP3): A cloud-native infrastructure for generic processing of SAR data* [Computer software]. https://doi.org/10.5281/zenodo.4646138

See [How to Cite HyP3 Products](https://hyp3-docs.asf.alaska.edu/usage_guidelines/).
