# PyPSA-Eur Pyrolysis Model

## Overview

This repository extends the PyPSA-Eur (v2025.07.0) energy system model by introducing a multi-output pyrolysis process based on sustainable biomass. The model and results presented in this repository were developed for the research paper "Sector-coupled European energy systems and the role of pyrolysis products in climate neutrality" for consideration by Energy Strategy Reviews (status: Submitted).

The main goal of the model is to represent pyrolysis as an energy conversion pathway that can simultaneously produce several useful energy carriers:

* Hydrogen
* Electricity
* Heat
* Synthetic fuels

The model allows the role of biomass-based pyrolysis to be evaluated within an integrated energy system. It can be used to analyse pyrolysis capacity, energy production, system costs, biomass consumption, and interactions with other energy technologies.

## Pyrolysis Configuration

The multi-output pyrolysis process can be enabled or disabled through the model configuration file.

In the configuration file, activate the multi-output pyrolysis option to include pyrolysis technologies in the energy system model.

When the option is enabled, the model includes:

* Sustainable biomass as the main pyrolysis input
* Multiple pyrolysis outputs
* Pyrolysis investment and operating costs
* Conversion efficiencies for each output
* Technical constraints associated with the pyrolysis process

When the option is disabled, the model runs without the pyrolysis technology and follows the standard model structure.

The relevant configuration option should be set to either `true` or `false`.

Example:

```yaml
  pyrolysis:
    enable: true 
```

## Downloading the Repository

The repository can be downloaded using Git.

```bash
git clone https://github.com/txelldm/pypsa-eur-pyrolysis.git
```


## Installation

The installation procedure follows the standard PyPSA-Eur workflow.

## Running the Model

Before running the model:

1. Select or create the appropriate configuration file.
2. Configure the required scenario parameters.
3. Enable or disable the multi-output pyrolysis option.
4. Check the biomass, technology, and network assumptions.
5. Run the workflow using Snakemake.

Example:

```bash
snakemake -call all --configfile config/config.pyrolysis.yaml 
```
## Pyrolysis Data

The economic and technical assumptions used for the pyrolysis technology are stored in the `data` folder.

The relevant file is:

```text
data/pyro_data.csv
```

This file contains the main technical and economic input data for the pyrolysis process ready to use in the model. 



## Acknowledgements

This model is based on the PyPSA-Eur framework version v2025.07.0.

PyPSA-Eur is an open-source energy system model developed using the PyPSA framework and the Snakemake workflow management system. This repository extends the original framework by adding a configurable multi-output pyrolysis pathway using sustainable biomass.
