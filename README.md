[![DOI](https://zenodo.org/badge/1432542013.svg)](https://doi.org/10.5281/zenodo.23627108)
---

# **<div align="center">Supplementary data for "Aseismic off-fault deformation reduces the earthquake potential inferred from geodesy"</div>**
### **<div align="center"> Nicolás Castro-Perdomo<sup>1</sup> and Kaj Johnson<sup>1</sup></div>**
### <div align="center"><sup>1</sup>Indiana University, Department of Earth and Atmospheric Sciences, Bloomington, Indiana 47405, U.S.A</div>



## Introduction

This repository contains the code, input data, and analyses performed in our study. 

## Folder structure

```
Natgeo_supplements/
├── README.md
├── requirements.txt
├── Inversion/                                    # SliDeFS Inversion Code (Johnson K, 2023) and input files 
├── Notebooks/
│   ├── strain_rate_analysis.ipynb                # geodetic strain-rate maps, variograms, threshold curve, moment tensors
│   ├── off_fault_geodetic_vs_seismic.ipynb       # off-fault seismic moment vs. geodetic budget (Monte Carlo null test)
│   ├── missing_fault_analysis.ipynb              # fault-length statistics and off-fault moment
│   ├── SAF_sensitivity_test.ipynb                # San Andreas fault sensitivity tests 
│   ├── trade_off_analysis.ipynb                  # trade-off analysis, accepted model ensemble 
│   ├── catalog_analysis_mc.ipynb                 # catalog moment budget vs. Monte Carlo null (Mueller C2 catalog)
│   └── neokinema_bird_2009.ipynb                 # NeoKinema (Bird, 2009) off-fault strain rates and moment rates
├── Input_data/
│   ├── modules/                                  # local Python modules
│   ├── datasets/                                 # strain rates, fault traces, threshold curve, moment-rate sources
│   ├── focal_mechanisms/                         # focal-mechanism catalogue, California polygon, NSHM2023 fault traces
│   ├── mc_cache/                                 # saved Monte Carlo results (.npz)
│   └── trade_off/                                # trade-off analysis
└── output_data/                                  # created/filled by the notebooks, one subfolder per notebook
```

## Dependencies

```
pip install -r requirements.txt
```

## How to run

Run each notebook from the `Notebooks/` folder. All paths are relative to it: inputs come from
`../Input_data/` and outputs go to `../output_data/<notebook name>/`.

```
cd Notebooks
jupyter lab                     # interactive
# or, non-interactively:
jupyter nbconvert --to notebook --execute --inplace strain_rate_analysis.ipynb
```

The notebooks are independent and can be run in any order. Approximate run times on a laptop:

| Notebook | Run time |
|---|---|
| strain_rate_analysis | ~2 min |
| off_fault_geodetic_vs_seismic | ~2 min |
| missing_fault_analysis | ~20 s |
| SAF_sensitivity_test | ~25 s |
| trade_off_analysis | ~15 s |
| catalog_analysis_mc | ~20 s |
| neokinema_bird_2009 | ~10 s |
