# Resources

!!! warning "Under review"
    This page was assembled by Claude (Anthropic) drawing on Dani Lindsay's thesis work, research notes, and guidance. It has not yet been through a final review — if you see this notice, treat the content as a useful starting point but verify anything you plan to cite or act on.

---

## Start here — ASF Storyboards

The Alaska Satellite Facility (ASF) have produced some of the best freely available InSAR learning materials. These interactive storyboards are well-made, visually clear, and require no prior experience. **Start with these.**

| Storyboard | What it covers |
|------------|---------------|
| [InSAR On Demand!](https://storymaps.arcgis.com/stories/68a8a3253900411185ae9eb6bb5283d3) | How to order interferograms using ASF's HyP3 on-demand processing — step by step |
| [Exploring Sentinel-1 InSAR](https://storymaps.arcgis.com/stories/8be186e4125741518118d0102e6835e5) | Walk through each output data layer using the 2019 Ridgecrest earthquake as an example. Example data included so you can follow along. |

The full ASF storyboard collection (SAR concepts, mission overviews, applications) is at:  
[https://asf-daac.maps.arcgis.com/home/index.html](https://asf-daac.maps.arcgis.com/home/index.html)

---

## Background reading

Short, accessible reads before you get into the processing.

- **ASF Introduction to SAR** — what SAR is and how it works, no maths required  
  [https://hyp3-docs.asf.alaska.edu/guides/introduction_to_sar/](https://hyp3-docs.asf.alaska.edu/guides/introduction_to_sar/)

- **NASA Earthdata SAR overview** — broader context on what SAR data is used for  
  [https://www.earthdata.nasa.gov/learn/earth-observation-data-basics/sar](https://www.earthdata.nasa.gov/learn/earth-observation-data-basics/sar)

- **EarthScope — How to read an interferogram** (one-page PDF, Wolf Volcano example)  
  [https://www.unavco.org/education/outreach/infographics/lib/images/InSAR-Basics-front.pdf](https://www.unavco.org/education/outreach/infographics/lib/images/InSAR-Basics-front.pdf)

- **USGS Fact Sheet — Monitoring Ground Deformation from Space**  
  [https://pubs.usgs.gov/fs/2005/3025/2005-3025.pdf](https://pubs.usgs.gov/fs/2005/3025/2005-3025.pdf)

- **ASF Sentinel-1 InSAR Product Guide** — what's inside the files you download  
  [https://hyp3-docs.asf.alaska.edu/guides/insar_product_guide/](https://hyp3-docs.asf.alaska.edu/guides/insar_product_guide/)

---

## Cloud processing — OpenSARLab

If you want to run MintPy without setting up a local environment, [OpenSARLab](https://opensarlab-docs.asf.alaska.edu/) is a managed JupyterHub provided by ASF with the main InSAR tools pre-installed. Log in with a NASA Earthdata account and run notebooks in the browser — no conda required.

---

## Useful GitHub repositories

Most InSAR software exists primarily on GitHub. Key repositories:

| Repository | What it is |
|------------|-----------|
| [insarlab/MintPy](https://github.com/insarlab/MintPy) | SBAS time series analysis — the tool you will use most |
| [insarlab/MintPy-tutorial](https://github.com/insarlab/MintPy-tutorial) | Worked example notebooks for MintPy |
| [comet-licsar/LiCSBAS](https://github.com/comet-licsar/LiCSBAS) | Time series from LiCSAR pre-processed Sentinel-1 stacks |
| [opera-adt/dolphin](https://github.com/opera-adt/dolphin) | Phase linking for dense time series — used in OPERA and NISAR product generation |
| [opera-adt/disp-s1](https://github.com/opera-adt/disp-s1) | OPERA Sentinel-1 surface displacement products |
| [isceplus/2025-isceplus](https://github.com/isceplus/2025-isceplus) | EarthScope 2025 InSAR short course notebooks |
| [isce-framework/isce2](https://github.com/isce-framework/isce2) | ISCE2 SAR processor (ALOS-1/2, Sentinel-1) |
| [isce-framework/isce3](https://github.com/isce-framework/isce3) | ISCE3 SAR processor (used for NISAR products) |

---

For academic references and key papers, see the [Literature](literature/keystone-papers.md) section. For short courses and scholarships, see [Scholarships & Community](community.md).
