# Installation

## Repository Setup
❗ Note: If you are a CDC user, please follow the set-up instructions found on Page X - CDC User Guide

Clone the repository to your local machine:

* `git clone https://github.com/CDCgov/tostadas.git`
## Environment Setup
❗ Note: If you have mamba or nextflow installed in your local environment, you may skip steps 1, 2 (mamba installation) and 5 (nextflow installation) accordingly.

(1) Install Mamba:
* `curl -L -O https://github.com/conda-forge/miniforge/releases/latest/download/Mambaforge-$(uname)-$(uname -m).sh`
* `bash Mambaforge-$(uname)-$(uname -m).sh -b -p $HOME/mambaforge`
(2) Add mamba to PATH:
* `export PATH="$HOME/mambaforge/bin:$PATH"`
(3) Create the conda environment:
If you want to create the full-conda environment needed to run the pipeline outside of Nextflow (this enables you to run individual python scripts), then proceed with step 3a.

If you want to run the pipeline using nextflow only (this will be most users), proceed with step 3b. Nextflow will handle environment creation and you would only need to install the nextflow package locally vs the entire environment.

       (3a) Create the conda environment and install the dependencies set in your environment.yml:

* `mamba env create -n tostadas -f environment.yml`   
       (3b) Create an empty conda environment:

* `conda create --name tostadas`
(4) Activate the environment.
* `conda activate tostadas`
Verify which environment is active by running the following conda command: conda env list . The active environment will be denoted with an asterisk *

(5) Install Nextflow using Use Mamba and the Bioconda Channel:
* `mamba install -c bioconda nextflow`
❗ Optionally, you may install nextflow without mamba by following the instructions found in the Nextflow Installation Documentaion Page: Nextflow Install