# A History of InSAR


!!! warning "Under review"
    This page was assembled by Claude (Anthropic) drawing on Dani Lindsay's thesis work, research notes, and guidance. It has not yet been through a final review — if you see this notice, treat the content as a useful starting point but verify anything you plan to cite or act on.

---


From the first radar images of glaciers to modern large-scale time series algorithms — InSAR has evolved rapidly over 40 years, driven by a handful of pivotal papers and the growing availability of free satellite data.

<p align="center">
  <img src="../../assets/InSAR_history.png" width="900"><br>
</p>

---

## Influential papers timeline

The table below traces key developments — from the earliest demonstrations of the technique through to the algorithms that underpin modern processing workflows. Papers are listed roughly chronologically within each theme.

| Year | Authors | Paper | Significance |
|------|---------|-------|--------------|
| 1974 | Graham | *Synthetic interferometer radar for topographic mapping* | Early theoretical foundation for SAR interferometry |
| 1986 | Gabriel & Goldstein | *Crossed orbit interferometry: theory and experimental results from SIR-B* | First demonstration of SAR interferometry from orbit |
| 1989 | Gabriel, Goldstein & Zebker | *Mapping small elevation changes over large areas: differential radar interferometry* | First use of InSAR to map surface deformation (agricultural subsidence) |
| 1993 | Massonnet et al. | *The displacement field of the Landers earthquake mapped by radar interferometry* | **First interferogram of a major earthquake** — demonstrated tectonic InSAR to the world |
| 1996 | Zebker & Goldstein | *Topographic mapping from interferometric SAR observations* | Established methods for DEM generation from InSAR |
| 1997 | Zebker et al. | *Atmospheric effects in interferometric SAR surface deformation and topographic maps* | Quantified the atmospheric noise problem that still challenges the field |
| 1998 | Ferretti, Prati & Rocca | *Nonlinear subsidence rate estimation using permanent scatterers in differential SAR interferometry* | Precursor to PSInSAR — first use of persistent point targets |
| 2000 | Ferretti, Prati & Rocca | *Nonlinear subsidence rate estimation using permanent scatterers* | **PSInSAR** — permanent scatterer time series |
| 2000 | Bürgmann, Rosen & Fielding | *Synthetic aperture radar interferometry to measure Earth's surface topography and its deformation* | Comprehensive review; essential reading |
| 2002 | Berardino et al. | *A new algorithm for surface deformation monitoring based on small baseline differential SAR interferograms* | **SBAS** — small baseline subset time series algorithm |
| 2002 | Pritchard & Simons | *A satellite geodetic survey of large-scale deformation of volcanic centres in the central Andes* | Landmark systematic survey of volcanic deformation |
| 2004 | Wright, Parsons & Lu | *Toward mapping surface deformation in three dimensions using InSAR* | Framework for combining ascending + descending to recover 3D motion |
| 2007 | Hooper et al. | *A new method for measuring deformation on volcanoes and other natural terrains using InSAR persistent scatterers* | StaMPS — PS time series for natural terrain (no urban infrastructure needed) |
| 2012 | Fattahi & Amelung | *InSAR uncertainty due to orbital errors* | Orbital ramp correction in time series |
| 2019 | Yunjun, Fattahi & Amelung | *Small baseline InSAR time series analysis: Unwrapping error correction and noise reduction* | **MintPy** — the current standard open-source SBAS time series tool |
| 2020 | Morishita et al. | *LiCSBAS: An open-source InSAR time series analysis package integrated with the LiCSAR automated Sentinel-1 InSAR processor* | **LiCSBAS** — time series integrated with automated COMET processing |
| 2021 | Zheng et al. | *Fast atmospheric correction for InSAR using ERA5 reanalysis data* | Operational tropospheric correction |

---

!!! note "This table is a starting point"
    It reflects a particular path through the literature — focused on tectonic, slow-slip, and landslide applications. The full history of InSAR is broader. Notable areas not covered here include DEM generation, ionospheric correction, and ice sheet applications.

---

## Key algorithm lineage

For a clearer picture of where the main processing chains came from, see [Getting Started](../getting-started.md) and the [Keystone Papers](keystone-papers.md) table.
