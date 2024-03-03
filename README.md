# Sugarcane yield prediction using RS and ML <img align="right" width="200px" src="https://www.omex.com/wp-content/uploads/2020/10/Sugar-Cane-Harvest-1536x772.jpg"/>

<p align='left'>
  <a href="#"><img src="https://img.shields.io/badge/repo%20status-100%25%20ready-green"></a>
  
  
## About
Tool created by Raul Roberto Poppiel (raulpoppiel@gmail.com) for the [FAPESP](https://fapesp.br/en) project Nº [23/01062-1](https://bv.fapesp.br/en/bolsas/207973/satellite-imagery-and-machine-learning-for-sugarcane-yield-estimation-in-regions-of-sao-paulo-state/) to utilize satellite imagery and machine learning techniques for accurate sugarcane yield estimation in regions of Sao Paulo state, Brazil.

This repository houses a comprehensive suite of scripts designed to facilitate the acquisition of remote sensing data for a diverse array of features (polygons). The primary objective is to support the prediction of sugarcane yield through the implementation of a Random Forest algorithm trained using more than 20,000 observed data. These scripts offer essential functionalities crucial for the seamless execution of this predictive modeling process, empowering researchers and practitioners in agricultural science to effectively harness remote sensing technologies for yield forecasting.

This repository comprises a comprehensive toolkit consisting of eight scripts meticulously crafted to streamline the management of geometries (shapefiles) and facilitate the acquisition of remote sensing time series data on vegetation indices and climate variables. Additionally, it enables the computation of the hydric balance tailored to your specific area of interest. These functionalities are integral to the process of generating inputs for yield predictions, leveraging a pre-fitted machine learning model provided within the repository. By seamlessly integrating these scripts into your workflow, you can effectively harness remote sensing technologies to enhance the accuracy of sugarcane yield forecasts.

## Core Functionalities (Python Colab Scripts should be run in the sequence)
1) **SHP_split.ipynb:** This script addresses the need to split large feature collections, containing over 1,000 polygons or field plots, into smaller collections with a fixed number of polygons. This helps to avoid computation issues, such as limitations on vertices, features, or memory within [Google Earth Engine (GEE)](https://earthengine.google.com/). The shapefile(s) containing polygons must be uploaded to GEE for their utilization in the subsequent scripts.
2) **climatic_data_daily.ipynb:** This script facilitates the retrieval of daily climatic data essential for computing hydric balance.
3) **climatic_data_monthly.ipynb:** Designed to fetch monthly climatic data required for use as a yield predictor.
4) **hydricBalance_data_monthly.ipynb:** Utilized to compute both daily and monthly hydric balance, serving as a critical yield predictor.
5) **sentinel2_data_monthly.ipynb:** Specifically crafted to retrieve monthly Sentinel-2 data, a crucial element for yield prediction.
6) **merge_data_all.ipynb:** This script merges all predictor data according to crop-season (referred to as SAFRA in Portuguese).
7) **outliers_analysis.ipynb:** Implemented to identify and remove potential outliers in sugarcane yield by crop-season (SAFRA).
8) **merge_safra_all.ipynb:** This script consolidates data from all crop-seasons (SAFRA) into a unified dataset.
9) **XXXXXXXXXXXX:** This script is responsible for employing the fitted prediction model alongside the predictors derived from your polygons or field plots to generate yield predictions.

## Data available for download
The `sugarcane_data.shp` file contains agronomic data with the following structure:
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
Please, cite the following paper when using this repository:

> Luciano, A.C.S., Second author, Third Author, 2024. Satellite imagery and machine learning for sugarcane yield estimation in regions of Sao Paulo state. Journal X, 116029. [https://doi.org/10.1016/j.geoderma.2022.116029](https://doi.org/10.1016/j.geoderma.2022.116029)
