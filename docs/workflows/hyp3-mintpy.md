# Time Series with HyP3 + MintPy

This workflow builds a displacement time series using **HyP3 multi-burst interferograms** processed on demand through ASF, and **MintPy** for the SBAS time series analysis.

This is the recommended workflow for students starting out — you do not need to install SAR processing software, and the entire pipeline runs in a Jupyter notebook.

---

## Overview

| Step | Tool | What happens |
|------|------|--------------|
| 1. Order interferograms | ASF HyP3 | Multi-burst Sentinel-1 interferograms processed in the cloud |
| 2. Download products | ASF / Python | Retrieve processed interferogram stacks |
| 3. Time series analysis | MintPy | SBAS inversion, noise correction, velocity estimation |
| 4. Visualisation | MintPy / PyGMT | Maps, time series plots, velocity fields |

---

## Why multi-burst?

Standard HyP3 interferograms cover a single Sentinel-1 burst (~80 km along-track). For most research targets — a fault segment, a landslide, a volcanic field — you need multiple adjacent bursts stitched together. Multi-burst processing handles this automatically and produces a single seamless interferogram over your area of interest.

!!! note "Ordering multi-burst products"
    Multi-burst ordering is done through the same ASF Vertex interface as single-burst. See [Ordering Your First Interferogram](single-interferogram.md) for the interface walkthrough — the steps are the same, just select multiple adjacent bursts for your area.

---

## MintPy

[MintPy](https://mintpy.readthedocs.io/) (Miami InSAR Time-series software in Python) is an open-source SBAS time series package. It ingests HyP3 products directly and is well documented and actively maintained.

**Key reference:** Yunjun, Z., Fattahi, H., & Amelung, F. (2019). Small baseline InSAR time series analysis: Unwrapping error correction and noise reduction. *Computers & Geosciences*, 133, 104331. [DOI](https://doi.org/10.1016/j.cageo.2019.104331)

### Installation

```bash
conda install -c conda-forge mintpy
```

Full environment file (including PyGMT): `environment.yml` in the repo root — coming soon.

### MintPy documentation

- [MintPy ReadTheDocs](https://mintpy.readthedocs.io/en/latest/)
- [HyP3 + MintPy demo dataset](https://mintpy.readthedocs.io/en/latest/demo_dataset/#sentinel-1_of_the_2019_ridgecrest_california_earthquake_sequence_with_hyp3) — 2019 Ridgecrest earthquake sequence, same dataset used in the ASF storyboards

---

## Example notebook

A worked example notebook for a New Zealand target area is in development and will be added here. It will cover:

1. Downloading a HyP3 multi-burst stack
2. Setting up the MintPy configuration file
3. Running the time series inversion
4. Plotting velocity maps and time series
5. Exporting results for visualisation in QGIS or PyGMT

---

## Useful resources

- [MintPy tutorials on GitHub](https://github.com/insarlab/MintPy-tutorial)
- [OpenSARlab](https://opensarlab-docs.asf.alaska.edu/) — run MintPy in a cloud Jupyter environment (no local install required)
- [EarthScope 2025 InSAR short course materials](https://github.com/isceplus/2025-isceplus) — includes MintPy notebooks
