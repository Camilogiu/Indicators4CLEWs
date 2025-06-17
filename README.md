## Introduction

*Indicators4CLEWs* is a flexible, open-source workflow designed to standardize the use of CLEWs (Climate, Land, Energy, and Water systems) model outputs. It supports the management and interpretation of modelling results, offering support to stakeholders and decision-makers.

This tool enhances the visualization of study outcomes, enabling both direct interaction with key parameters—such as forest area ratio, agricultural land use, and the share of irrigated land—and broader, cross-sectoral analyses. These may include indicators not strictly confined to CLEWs, such as the Biodiversity Index or the average annual water stress.  

---

## Features

- Conversion of `data.txt` and `results.txt` files into `.csv` file.
- Uses `otoole` for data and results conversions.
- Converts the results into 5 .csv files divided based on modes of operation or time-slices.
- Flexible naming based on the convention adopted by the user.
- Visualization of the results with matplotlib.

---

## Prerequisites

1. Install Anaconda:  
   https://www.anaconda.com/products/distribution

2. Clone this repository

3. Create and activate the environment:
```bash
conda env create -f otoole.yml
conda activate otoole-env
```
---

## Supported Input Versions

This script supports `.txt` input files generated from OSeMOSYS `MUIO Version 5.0 or higher`. 

---

## Usage

Select your model on MUIO and download the `data.txt` and the `results.txt` files. Place both .txt files in the folder `convert_from`. Then define your naming convention and select the indicators you are interested into in the first part of the notebook called `Configuration`. The user will have to specify:

- In the subsection `Indicators`: if the indicator is of interest (with the bolean True (of interest) or False).
- In the subsection `Naming convention`: the naming convention adopted (e.g what are the crop names, which are the managment levels etc.)

Once this is done you can run the notebook.

Note that if the indicator is of interest, the user will also have to make sure that it is feasible according to the model. For example, it is not possible to display the indicator *Forest_share* if there is no *forest* technolgy.

Before modifying the notebook, you can use the data in the `Test` folder for testing the worflow and its functionalities.

## Notebook structure

The first four sections of the Jupyter Notebook will create three new directories called `Data`, `Plots`, and `Results` and convert both the input and output file into .csv files. Note that due to a matter of file format, the data.txt file will be converted into a new `data_fixed.txt` file which will appear in the convert_from directory.

In the `Data` folder, the user will find two new subfolders called `Model input` and `Model output`. The first one has the converted input data coming from the data_fixed.txt file, while the latter contains the converted model results coming from the results.txt file.

Sections 5 and 6 are where the indicators are created and visualized. 

Each part of the Notebook and each indicator (meaning and formulas) will be further explained in the notebook and the user will be guided through each step.

---

## Folder Structure After Running

```
.
├── convert_from/
│   └── data_fixed.txt
    └── data.txt
    └── results.txt
├── Data/
│   └── Model input
        └── ...
    └── Model output
        └── ...
├── Plots/
│   └── ...
├── Results/
│   └── ...
├── Test
│   └── ...
├── otoole.yml
├── model.v.5.2.txt
├── config_com.yaml
├── Indicators.jpynb
```
---

## Release Notes - version 1.0 (2025)

- Make sure the following files exist in the same folder before running:
  - `model.v.5.2.txt` — OSeMOSYS model formulation file 
  - `config_com.yaml` — Otoole configuration file for mapping input/output parameters.

- The available indicators are:
  - Forest cover
  - Harvested area
  - Irrigated area
  - Net emissions
  - Crop Yield
  - BHI - Biodiversity Habitat Index
  - Relative annual water demand
  - Annual average water stress score
  - Crop_IDR - Crop Import Dependency Ratio
  - Harvested area under high managment
---

The model.v.5.2.txt and the config_com.yaml files were taken from the repository OSeMOSYS-Solver-script (https://github.com/ShravanKumar23/OSeMOSYS-Solver-script/tree/main). The part of the code used for converting the data.txt file into .csv files and for fixing the data.txt file, was taken and dapted to this workflow from the same repository.

---

## License

MIT License

## Contributors:
------------------------------------------------
**[Camilla Lo Giudice](https://github.com/Camilogiu)** - Developer<br />
**[Francesco Gardumi]** - Supervisor<br />
**[Daniel Adshead]** - Co-supervisor<br />

## Acknowledgements

- [OSeMOSYS](https://www.osemosys.org/)
- [otoole](https://otoole.readthedocs.io/en/latest/)
- MUIO OSeMOSYS User Interface
- [IAMCOMPACT](https://www.iam-compact.eu/) project has received funding from the European Union's HORIZON EUROPE Research and Innovation Programme under grant agreement No 101056306. 
