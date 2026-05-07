# Making Maps with PyGMT


!!! warning "Under review"
    This page was assembled by Claude (Anthropic) drawing on Dani Lindsay's thesis work, research notes, and guidance. It has not yet been through a final review — if you see this notice, treat the content as a useful starting point but verify anything you plan to cite or act on.

---


[PyGMT](https://www.pygmt.org/) is a Python interface to the Generic Mapping Tools (GMT) — the standard tool for publication-quality geoscience maps. It works well in Jupyter notebooks, which makes it straightforward to combine with InSAR data analysis.

---

## Installation

```bash
conda install -c conda-forge pygmt
```

A full environment file including PyGMT alongside common InSAR analysis packages is available in the repo root (`environment.yml` — coming soon).

---

## Example notebooks

Notebooks will be added here as examples are developed. Each covers a specific mapping task relevant to InSAR interpretation.

| Notebook | Description |
|----------|-------------|
| *Coming soon* | Basic map of NZ with fault traces and SAR frame coverage |
| *Coming soon* | Plotting an unwrapped interferogram with a custom colourmap |
| *Coming soon* | Velocity map from MintPy output with hillshade background |

---

## Useful resources

- **PyGMT documentation:** [https://www.pygmt.org/latest/](https://www.pygmt.org/latest/)
- **PyGMT gallery:** [https://www.pygmt.org/latest/gallery/](https://www.pygmt.org/latest/gallery/) — good source of copy-paste examples
- **GMT forum:** [https://forum.generic-mapping-tools.org/](https://forum.generic-mapping-tools.org/)
