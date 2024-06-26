<p align='center'>
  <a href="#"><img  width="300px" src="https://fealq.org.br/esalqshow/wp-content/uploads/2021/04/03-Esalq-USP-Horizontal-Digital-VERDE-768x183.png"></a>
  <a href="#"><img  width="300px" src="https://fapesp.br/assets/img/logo-simple2.png"></a>


# Sugarcane yield prediction using RS and ML <img align="right" width="200px" src="https://www.omex.com/wp-content/uploads/2020/10/Sugar-Cane-Harvest-1536x772.jpg"/>

<p align='left'>
  <a href="#"><img src="https://img.shields.io/badge/repo%20status-100%25%20ready-green"></a>
  
  
## About
Scripts elaborated by Raul Roberto Poppiel (raulpoppiel@gmail.com) for the [FAPESP](https://fapesp.br/en) project Nº [23/01062-1](https://bv.fapesp.br/en/bolsas/207973/satellite-imagery-and-machine-learning-for-sugarcane-yield-estimation-in-regions-of-sao-paulo-state/), led by Professor Ana Claudia dos Santos Luciano ([analuciano@usp.br](analuciano@usp.br)) from ESALQ/USP, Brazil. These scripts leverage satellite imagery and machine learning techniques for sugarcane yield estimation in regions of Sao Paulo state, Brazil. The methodology is outlined in the [MSc Dissertation](https://doi.org/10.11606/D.11.2023.tde-02102023-163947) by Rafaella Pironato Amaro.

This repository contains a comprehensive suite of scripts aimed at streamlining the acquisition of remote sensing data for sugarcane plots (polygons), with the primary goal of facilitating the prediction of sugarcane yield. Through the utilization of a Random Forest algorithm trained on a dataset comprising over 20,000 observed sugarcane yield records, the scripts enable users to retrieve remote sensing time series data on vegetation indices and climate variables across your specific areas of interest. These datasets serve as inputs to the trained model provided for accurate sugarcane yield predictions. See model perfomance report in the specific folder in this repo. 

## To import this github repo into your Google Drive using Colab, follow the steps:
In the first cell from [Colab](clone_Git_repo_to_GD.ipynb), import the drive package and mount you google drive:

```
from google.colab import drive
drive.mount('/content/drive')
```

In the next cell, past the following script to clone this repo into your Google Drive:
```
import os
from pathlib import Path
out_path = '/content/drive/MyDrive/Colab Notebooks/'

if not os.path.exists(out_path):
  Path(out_path).mkdir(parents=True, exist_ok=True)
  print("Output directory created successfully.")
else:
  print("Output directory already exists.")

%cd "{out_path}"
!git clone https://github.com/raulpoppiel/sugarcane-yield-prediction.git
```
Go to folder "Colab Notebooks" in your GD to find this repo.

## Core Functionalities (Python Colab Scripts should be run in the sequence)
1) **climatic_data_daily.ipynb:** This script facilitates the retrieval of daily climatic data essential for computing hydric balance.
2) **climatic_data_monthly.ipynb:** Designed to fetch monthly climatic data required for use as a yield predictor.
3) **sentinel2_data_monthly.ipynb:** Specifically crafted to retrieve monthly Sentinel-2 data, a crucial element for yield prediction.
4) **trained_prediction_model:** This script is responsible for employing the fitted prediction model alongside the predictors derived from your polygons or field plots to generate yield predictions.

## Data available for download
For a reproducible example, the [`sugarcane_data`](https://github.com/raulpoppiel/sugarcane-yield-prediction/tree/main/01_SugarcaneYieldPrediction/01_input_data) file contains agronomic data with the following structure:
- 'ID_SIG': 'X19200890000003600027002', 🟢
- 'AREA': 46.0963242244,
- 'BLOCO': 2,
- 'CODFAZ': 36,
- 'COD_USINA': 89,
- 'EST_Corte': 1, 🟢
- 'Local': 'Usina 3',
- 'Ordem': 'Latossolos', 🟢
- 'POL': 0,
- 'SAFRA': '1920', 🟢
- 'SAFRA_real': 1819, 🟢
- 'TAH': 0,
- 'TALHAO': 17002,
- 'TCH_ANT': 88.875, 🟢
- 'Unidade_So': 'LV21',
- 'VAR': 'CTC4',
- 'VARIEDADE': 'CTC4',🟢
- 'relevo': 'Suave Ondulado',
- 'soloGeral': 'LV',
- 'usina': 'M3'

🟢 Green balls indicate mandatory fields in your data. Please ensure attention to both lower and upper cases. 

## Reference
Please, cite the following paper (currently under development) when using this repository:

> Luciano, A.C.S., Second author, Third Author, 2024. Satellite imagery and machine learning for sugarcane yield estimation in regions of Sao Paulo state. Journal X, 116029. [https://doi.org](https://www.sciencedirect.com/)
