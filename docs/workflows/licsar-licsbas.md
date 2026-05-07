# Time Series with LiCSAR + LiCSBAS

This workflow builds a displacement time series using **LiCSAR** pre-processed interferograms and the **LiCSBAS** time series analysis toolkit.

**Background**

To monitor deformation through time, many interferograms are combined to generate displacement time series. This improves signal-to-noise and resolves subtle signals that evolve slowly — such as gradual inflation, interseismic strain, or slow landslide creep — over periods of weeks to years.

A primary data source for this workflow is the automated processing system developed by the **Centre for the Observation and Modelling of Earthquakes, Volcanoes and Tectonics ([COMET](https://comet.nerc.ac.uk/))** at the University of Leeds. COMET produces Sentinel-1 interferograms for volcanic and tectonic regions worldwide, distributed through the **LiCSAR** system:  
[https://comet.nerc.ac.uk/COMET-LiCS-portal/](https://comet.nerc.ac.uk/COMET-LiCS-portal/)

LiCSAR products are processed with [GAMMA](https://www.gamma-rs.ch/gamma-software) and delivered in a consistent geographic reference frame, making them well suited for time series analysis without requiring you to run full interferometric processing yourself.

For time series generation, LiCSAR products integrate directly with **[LiCSBAS](https://github.com/comet-licsar/LiCSBAS)** — an open-source toolkit for constructing displacement time series, velocity maps, and quality metrics from LiCSAR interferogram stacks.

<p align="center">
  <img src="../../assets/LiCSAR_project.png" width="600"><br>
  <em>COMET-LiCS: Sentinel-1 InSAR portal.</em>
</p>

!!! tip "Pros and cons"
    **Pros:** Fixed geographic frame, pre-processed stacks ready to use, well-documented pipeline.  
    **Cons:** Processing runs on a quarterly cycle, so there is a delay between data acquisition and updated products being available.

<p align="center">
  <img src="../../assets/LiCSBAS_timeseries.png" width="600"><br>
  <em>LiCSBAS time series output.</em>
</p>

---

## LiCSBAS Installation (Ubuntu / Linux)

These instructions install LiCSBAS using a Conda environment — the recommended method as it handles all dependencies automatically.

### 1. Install Miniconda

!!! warning
    Only do this once. Check if you already have Conda installed (`conda --version`) before proceeding.

```bash
mkdir -p ~/tools && cd ~/tools
wget https://repo.anaconda.com/miniconda/Miniconda3-latest-Linux-x86_64.sh
bash Miniconda3-latest-Linux-x86_64.sh
```

Restart your terminal, then verify:

```bash
conda --version
```

### 2. Clone LiCSBAS

```bash
cd ~/tools
git clone https://github.com/comet-licsar/LiCSBAS.git
cd LiCSBAS
```

### 3. Create and activate the Conda environment

```bash
conda env create -f environment.yml   # takes a few minutes
conda activate licsbas
```

You should see `(licsbas)` at the start of your terminal prompt.

### 4. Add LiCSBAS to your PATH

```bash
# Get your install path
cd ~/tools/LiCSBAS && pwd
```

Add the following to `~/.bashrc`, replacing the path with your output from above:

```bash
export LiCSBAS=~/tools/LiCSBAS
export PATH=$PATH:$LiCSBAS/bin
export PYTHONPATH=$PYTHONPATH:$LiCSBAS/LiCSBAS_lib
```

Reload:

```bash
source ~/.bashrc
```

### 5. Test the installation

```bash
conda activate licsbas
LiCSBAS_check_install.py
```

If the command and library checks pass, you are ready to go.

<p align="center">
  <img src="../../assets/LiCSBAS_terminal_1.png" width="600"><br>
  <em>Successful LiCSBAS install check output.</em>
</p>

---

## Troubleshooting

If you encounter errors, the most reliable fix is: quit the terminal, reopen, reactivate the environment, and re-run the install check.

```bash
conda activate licsbas
LiCSBAS_check_install.py
```

If the PATH check fails, verify that the path you added to `.bashrc` matches the output of `pwd` in your LiCSBAS directory.

---

## Training

With the software installed, follow the tutorial **"LiCSBAS_sample_CF.pdf"** available on [GitHub](https://github.com/comet-licsar/LiCSBAS?tab=readme-ov-file#sample-products-and-tutorial).

You can skip section 1 (Preparation) — the install instructions above cover it. Start at **"2. Quick Start"**.

<p align="center">
  <img src="../../assets/LiCSBAS_tutorial.png" width="600"><br>
  <em>LiCSBAS tutorial document.</em>
</p>

---

## Acknowledgements

When using LiCSAR data, include the following acknowledgement:

> "LiCSAR contains modified Copernicus Sentinel data [year] analysed by the Centre for the Observation and Modelling of Earthquakes, Volcanoes and Tectonics (COMET). LiCSAR uses JASMIN, the UK's collaborative data analysis environment (http://jasmin.ac.uk)."

Key citations:

> Lazecký, M. et al. (2020). LiCSAR: An Automatic InSAR Tool for Measuring and Monitoring Tectonic and Volcanic Activity. *Remote Sensing*.

> Morishita, Y. et al. (2020). LiCSBAS: An Open-Source InSAR Time Series Analysis Package Integrated with the LiCSAR Automated Sentinel-1 InSAR Processor. *Remote Sensing*, 12, 424.

See [Acknowledging LiCSAR products](https://comet.nerc.ac.uk/COMET-LiCS-portal/) for full citation guidance.
