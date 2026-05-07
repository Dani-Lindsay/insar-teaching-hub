# Is Something Happening Now? Lets make an interferogram!

This workflow is used when there is concern about possible new volcanic deformation.

Examples:

* Increased seismicity
* Changes in gas emissions
* Ground cracking reports
* Change in GPS time series
* Unrest alerts

The goal is to quickly assess whether deformation is occurring.

> 🚫 **STOP**
> If you have send a signal in the GNSS displacements and are wondering whether it should be visible with InSAR, use the [GNSS Forward Model](use_cases/03_forward_modelling.md) to simulate the expected displacement field and determine whether you would expect to see it in an interferogram before you go through the process below.

**Background**  
Currently, the Sentinel-1 constellation has two satellites that orbit (satellites A and C), collecting SAR images every 6–12 days in each orbit direction. Once an observation has been made, there is some delay time in downloading the data and it becoming available (6–24 hrs). A quick and simple way to generate an interferogram is to use the Alaska Satellite Facility's ([ASF](https://asf.alaska.edu/)) Hybrid Pluggable Processing Pipeline, or [HyP3](https://hyp3-docs.asf.alaska.edu/about/) (pronounced "hype") — a cloud-native processing platform developed to efficiently process Synthetic Aperture Radar (SAR) imagery. This is a low-latency option to generate on-demand interferograms processed with [GAMMA](https://www.gamma-rs.ch/gamma-software) software.

***Pro's*** Able to get interferograms within ~24 hrs of an observation

***Con's*** This process grabs the whole frame so larger region than required. The frames shift over time so you don't always return an interferogram that covers your geographic target. 

---

## Training: Ordering Sentinel-1 InSAR datasets from the ASF

1. Please follow this [InSAR On Demand!](https://storymaps.arcgis.com/stories/68a8a3253900411185ae9eb6bb5283d3) storyboard from ASF to learn how to navigate ordering interferograms online. More detailed descriptions of data ordering, processing algorithms, and parameter choices are available in the [Sentinel-1 InSAR Product Guide](https://hyp3-docs.asf.alaska.edu/guides/insar_product_guide/).

<p align="center">
  <img src="../assets/ASF_InSAR_OnDemand_StoryBoard.png" width="600"><br>
  <em>ASF Storyboard training for ordering data using HyP3 On-Demand tools.</em>
</p>

2. Next, explore the products you have downloaded with the [Exploring Sentinel-1 InSAR](https://storymaps.arcgis.com/stories/8be186e4125741518118d0102e6835e5) storyboard. These step through each data layer using the 2019 Ridgecrest Earthquake as an example. At the bottom of the storyboard is the example dataset they use so you can also download and follow along.

> **Note**  
> The Ridgecrest Earthquake was captured beautifully with InSAR, and most locations have vegetation, topography, and atmospheric signals overprinting the displacement fields. This is still a useful exercise so you can explore what "good" data look like before stepping straight into challenging data.

<p align="center">
  <img src="../assets/Getting_to_know_S1.png" width="600"><br>
  <em>ASF Storyboard training for exploring the Sentinel-1 products generated with ASF's HyP3 On-Demand tool.</em>
</p>

---

## Example: Ordering an On-Demand Interferogram

> [!WARNING]
> These are not exhaustive instructions — please follow the storyboards above to familiarise yourself with the process of ordering and retrieving data. Below are snapshots of the process of ordering data for a target area.

1. Select your geographic area of interest
2. Select the time window of interest, last ~1–2 months

<p align="center">
  <img src="../assets/ASF_DataVertex_example.png" width="600"><br>
  <em>Search for data on ASF Data Vertex and select your area of interest.</em>
</p>

3. Use "SBAS" tool to select the pairs you would like to order.
4. Submit to the On-Demand List

<p align="center">
  <img src="../assets/ASF_SBAS_order.png" width="600"><br>
  <em>Select interferogram pairs.</em>
</p>

5. Select processing parameters. See product guide: https://hyp3-docs.asf.alaska.edu/guides/insar_product_guide/ for detailed descriptions.

6. Submit the processing job. This can take a few hours depending on how many interferograms you have ordered.

<p align="center">
  <img src="../assets/ASF_SBAS_SubmitJob.png" width="600"><br>
  <em>Submit HyP3 job</em>
</p>

7. Check status of running jobs. 

<p align="center">
  <img src="../assets/ASF_Status.png" width="600"><br>
  <em>Check status of HyP3 job</em>
</p>

---

## Step 2 — Download Products

1. Add products to the list, download the Python script.

<p align="center">
  <img src="../assets/ASF_downloads.png" width="600"><br>
  <em>Select finished interferogram products to download locally.</em>
</p>

2. Move the download script to where you want the data. Open the terminal in the data directory. Run the download script. It will ask you to enter your credentials — these are the same as the ASF Data Vertex website we ordered the data from.

<p align="center">
  <img src="../assets/ASF_Download_data.png" width="800"><br>
  <em>Download the interferogram products to your computer.</em>
</p>

3. Explore the data products!! Enjoy!

Check out the ASF [Exploring Sentinel-1 InSAR](https://storymaps.arcgis.com/stories/8be186e4125741518118d0102e6835e5). This storyboard explores the Sentinel-1 products using the 2019 Ridgecrest Earthquake as an example.

---

## Step 3 — Initial Interpretation

Look for:

* Concentric fringes → Inflation/deflation
* Linear gradients → Tectonic or atmospheric
* Low coherence → Landcover change from Vegetation / New Ash Fall / Landslide

> **Check out** 
> EarthScope (UNAVCO) [How to read an interferogram](https://www.unavco.org/education/outreach/infographics/lib/images/InSAR-Basics-front.pdf?) - Wolf Volcano, Galápagos Islands, Ecuador

If you would like to do more with Hyp3 products check out [MintPy](https://mintpy.readthedocs.io/en/latest/) time series software. MintPy can [Hyp3](https://mintpy.readthedocs.io/en/latest/demo_dataset/#sentinel-1_of_the_2019_ridgecrest_california_earthquake_sequence_with_hyp3) products directly and is well documented and supported.  

For inspiration, here is Figure 1 from [Pritchard & Simons (2002)](https://www.nature.com/articles/nature00872). 

<p align="center">
  <img src="../assets/Pritchard_Simons_2002.jpg" width="400"><br>
  <em>Figure 1 from Pritchard & Simons (2002) showing examples of volcanic deformation detected using satellite InSAR across the Central Andes. Interferometric colour fringes (draped over topography) indicate surface displacement in the radar line-of-sight direction, where each full colour cycle represents ~5 cm of motion. Circular fringe patterns highlight inflating and deflating volcanic centres, demonstrating how InSAR can be used to identify and monitor active deformation.</em>
</p>



<p align="center">
  <img src="../assets/View_Google_Earth.png" width="600"><br>
  <em>View .kmz files in Google Earth</em>
</p>

<p align="center">
  <img src="../assets/View_QGIS.png" width="600"><br>
  <em>View .tiff files in QGIS</em>
</p>

## Acknowledgement 

When using the HyP3 product in reports, presentations or publications please use the correct acknowledgement:

> Hogenson, K., Kristenson, H., Kennedy, J., Johnston, A., Rine, J., Logan, T., Zhu, J., Williams, F., Herrmann, J., Smale, J., & Meyer, F. (2020). *Hybrid Pluggable Processing Pipeline (HyP3): A cloud-native infrastructure for generic processing of SAR data* [Computer software]. https://doi.org/10.5281/zenodo.4646138  

See [How to Cite HyP3 Products](https://hyp3-docs.asf.alaska.edu/usage_guidelines/)
