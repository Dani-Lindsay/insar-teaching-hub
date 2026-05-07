# About


!!! warning "Under review"
    This page was assembled by Claude (Anthropic) drawing on Dani Lindsay's thesis work, research notes, and guidance. It has not yet been through a final review — if you see this notice, treat the content as a useful starting point but verify anything you plan to cite or act on.

---


## Hi, I'm Dani

I'm an InSAR Scientist at [ESNZ](https://www.gns.cri.nz/) (Earth Sciences New Zealand), based in Wellington. My background is in geology and geophysics — I studied at Victoria University of Wellington before completing a PhD at UC Berkeley, and I've spent most of my career trying to make satellites tell us something useful about how the ground moves.

I'm curious about the places where slow, steady processes tip into something more dramatic — creeping faults that lock up, landslides that accelerate, volcanic systems that quietly inflate for years before anything happens. InSAR is well-suited to this kind of problem because it's dense, repeatable, and indifferent to whether the deformation is happening somewhere accessible or not.

---

## Research background

**Honours (VUW, 2017)** — GPS analysis across the central Southern Alps, spanning the Alpine Fault 30 km south of its intersection with the Hope Fault. Processed continuous and campaign GPS data through GAMIT/GLOBK, estimated coseismic and postseismic signals from six large earthquakes including Kaikōura, and modelled the resulting velocity field with a screw dislocation to constrain Alpine Fault locking depth and slip rate.

**MSc (VUW, 2019)** — Geodetic investigation of triggered slip below Fiordland, following the 2016 M7.8 Kaikōura earthquake. Examined whether the earthquake triggered slow slip events in the Puysegur subduction zone using GPS time series.

**PhD (UC Berkeley, 2025)** — Multiscale surface deformation in Northern California from L-band InSAR. Three chapters:

- **Regional velocity fields**: nine years of ALOS-2 ScanSAR data across Northern California, from the Oregon border to San Francisco. Validated against GNSS, resolved long-wavelength deformation including drought-driven aquifer subsidence, volcanic subsidence at Medicine Lake, and seasonal landslide motion.
- **Fault creep**: surface creep rates and their temporal variability along the Maacama and Rodgers Creek faults using InSAR, alignment arrays, and repeating microearthquake catalogs. Documented a notable creep event in 2002 and multi-year suppression of creep afterward — with implications for seismic hazard assessment.
- **Slow landslides**: kinematic response of over 400 slow-moving landslides to precipitation and earthquake shaking, 2021–2024. Found spatial clustering of triggered accelerations correlated with the directivity of a 2022 M6.4 earthquake, and fitted a piecewise model to characterise the recovery timescale (~16 months to return to 90% of pre-event rates).

**Current work (ESNZ, 2025–present)** — L- and C-band InSAR for landslide monitoring, tectonic strain accumulation, and transient volcanic and tectonic deformation across New Zealand. Developing operational InSAR workflows using NISAR GSLCs, Sentinel-1, and ALOS-1/2 archive data.

---

## Tools and methods

- **SAR processing**: ISCE2 (alosStack for ALOS-2 ScanSAR, stripMap for ALOS-1), ISCE3/COMPASS (Sentinel-1), some GMTSAR experience
- **Time series**: MintPy (primary), Dolphin (phase linking for NISAR GSLC and Sentinel-1)
- **Plotting**: PyGMT, Matplotlib
- **Languages**: Python, bash; some MATLAB

---

## Teaching

I've been a teaching assistant across a range of courses at VUW and Berkeley:

| Course | Institution | Years |
|--------|-------------|-------|
| EPS 20: Earthquakes in Your Backyard | UC Berkeley | 2024 |
| EPS 116: Structural Geology and Tectonics | UC Berkeley | 2020, 2022 |
| ESCI 342: Structural Field Geology (Kekerengu) | VUW | 2017, 2018, 2019 |
| ESCI 302: Structural Geology | VUW | 2018 |
| ESCI 111: Introduction to Physical Geography and Earth Sciences | VUW | 2016 |

---

## Publications

*In preparation / in press — list will be updated as papers are published.*

- **Lindsay, D.**, & Bürgmann, R. (*in prep*). 3D Velocity Field From L-Band InSAR Reveals Multi-Scale Tectonic and Non-tectonic Deformation in Northern California.
- **Lindsay, D.**, Taira, T., & Bürgmann, R. (*in prep*). Temporal and Spatial Creep Variability: Detecting Decadal Changes in Fault Behavior in Northern California.
- **Lindsay, D.**, Taira, T., & Bürgmann, R. (*in prep*). Slow-Moving Landslide Response to Earthquake Shaking and Atmospheric Rivers in Northern California From 2021–2024 InSAR Time Series.
- Materna, K., Bürgmann, R., **Lindsay, D.**, et al. (2024). Shallow slow slip events in the Imperial Valley with along-strike propagation. *Geophysical Research Letters*, 51(12), e2023GL108089.
