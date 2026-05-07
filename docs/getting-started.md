# Getting Started with InSAR

!!! warning "Under review"
    This page was assembled by Claude (Anthropic) drawing on Dani Lindsay's thesis work, research notes, and guidance. It has not yet been through a final review — if you see this notice, treat the content as a useful starting point but verify anything you plan to cite or act on.

---

**What is InSAR, how does it work, and what to watch out for when interpreting data.**

For links to tutorials, courses, and tools — see [Resources](resources.md).

---

## What is InSAR?

**Interferometric Synthetic Aperture Radar (InSAR)** is a satellite-based technique for measuring ground surface deformation at centimetre to millimetre scales. It has transformed our understanding of interseismic and transient deformation by providing high-resolution, repeat observations that cover entire landscapes — without fieldwork, without clear skies, and regardless of whether the deforming area is accessible.

<p align="center">
  <img src="../assets/SAR_basics.png" width="700"><br>
  <em>Conceptual overview of SAR acquisition geometry and radar line-of-sight (Simons & Rosen, 2015).</em>
</p>

---

## How it works

A SAR satellite transmits pulses of microwave energy and records the signal reflected back from the ground. Each pixel in a SAR image contains two pieces of information: **amplitude** — the strength of the return, which depends on how much energy the surface scatters back — and **phase**, which encodes the two-way travel time between the satellite and that point on the ground. Rocks, vegetation, and buildings all scatter microwave energy differently, depending on the radar wavelength and look angle.

By combining two SAR images acquired from nearly the same orbital position at different times, we form an **interferogram**. The interferometric phase at each pixel is:

$$\phi_I = \phi_1 - \phi_2 = \frac{4\pi}{\lambda}\,\delta\rho$$

where $\lambda$ is the radar wavelength and $\delta\rho$ is the change in satellite-to-ground distance between the two passes. If the ground has moved toward or away from the satellite, that motion appears as a phase shift. In the final image, phase differences are displayed as colour fringes — one full colour cycle represents ground motion of **half a radar wavelength** in the line-of-sight direction (~2.8 cm for Sentinel-1 C-band, ~11.8 cm for ALOS-2 L-band).

A single interferogram captures the integrated deformation over one time interval. By stacking many interferograms from overlapping time windows — the SBAS approach — a displacement time series can be derived and slow signals separated from noise. Tools like MintPy and LiCSBAS implement this.

### Wavelength matters

Currently operating SAR satellites carry sensors with wavelengths of around 3 cm (X-band), 6 cm (C-band), and 23 cm (L-band). Longer wavelengths penetrate further into vegetation and maintain coherence over vegetated terrain — a significant advantage in New Zealand, where C-band data often decorrelates over native bush and pasture. The tradeoff is greater sensitivity to the ionosphere at L-band (see [Ionospheric Effects](concepts/ionosphere.md)).

### Three dimensions from multiple passes

InSAR measures displacement only in the radar line-of-sight — a mixture of vertical and east–west horizontal motion. Separating the components requires observations from both ascending (south-to-north) and descending (north-to-south) passes. Adding GNSS constraints allows the full 3D velocity field to be estimated, though north–south accuracy remains limited by the near-polar satellite orbits.

Modern satellites like Sentinel-1 and ALOS-2 use a **ScanSAR** acquisition mode, sweeping the radar beam across multiple sub-swaths to cover wide areas (~250–350 km). Each sub-swath is illuminated in short bursts — understanding this geometry is important when selecting data and choosing between single-burst and multi-burst processing.

<p align="center">
  <img src="../assets/ScanSAR_geometry_simons2015.png" width="600"><br>
  <em>ScanSAR acquisition geometry showing the burst-and-subswath structure. The radar transmits a burst of pulses to subswath 1 then switches electronically to subswaths 2 and 3. Burst overlap between subswaths allows construction of continuous maps. From Simons & Rosen (2015).</em>
</p>

---

## Common sources of misinterpretation

Each interferogram contains contributions from ground displacement, topography, tropospheric delays, ionospheric phase advances, orbital errors, changes in surface scattering, and phase noise — not just deformation. Before interpreting any pattern, consider each of the following.

1. **Atmospheric delay** — tropospheric and ionospheric signals can produce fringe patterns that closely resemble real deformation. Tropospheric signals tend to correlate with topography; ionospheric signals produce long-wavelength, range-parallel ramps, particularly in L-band data.
2. **Phase unwrapping errors** — discontinuities or false bullseyes introduced during the unwrapping step. Especially common in low-coherence areas and near steep phase gradients.
3. **Geometric effects** — layover and radar shadow in steep terrain produce missing data and apparent discontinuities with no geophysical meaning.
4. **Line-of-sight ambiguity** — a single interferogram mixes vertical and horizontal motion. Separating the two requires ascending and descending tracks, GNSS constraints, or modelling.
5. **Coherence loss** — low coherence does not indicate deformation; it indicates the phase is unreliable. Coherence degrades when the surface changes between passes (vegetation, snow, landslide scarps, flooding) or when deformation gradients exceed what the phase can track continuously.

---

Key papers for these concepts are listed in the [Keystone Papers](literature/keystone-papers.md) table.
