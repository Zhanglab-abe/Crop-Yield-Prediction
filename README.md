# [Sensing and Automation in Agri-System (SAAS) Lab](https://sites.google.com/view/xin-zhang-lab/home)

[**Department of Agricultural & Biological Engineering**](https://www.abe.msstate.edu/)

[**Mississippi State University**](https://www.msstate.edu/)

# Why do we create this repo?
*This repo is created for participating the 3rd International Workshop on Machine Learning for Cyber-Agricultural Systems: [**MLCAS2021 Crop Yield Prediction Challenge**](https://eval.ai/web/challenges/challenge-page/1251/overview). Our team ("AA2") was ranked Top 5 in the competition among 29 teams.*

# Who owns the data shared in this repo?
*This repo is owned by the [Sensing and Automation in Agri-System (SAAS) Lab](https://sites.google.com/view/xin-zhang-lab/home) in the Department of Agricultural & Biological Engineering at Mississippi State University. Please contact the lab PI, [Dr. Xin Zhang](https://www.abe.msstate.edu/people/faculty/xin-zhang/), if you have any questions regarding this repo.*

# How to use this repo?
*We achieved the best prediction accuracy of **soybean** crop yield using [**XGBoost**](https://xgboost.readthedocs.io/en/stable/). The complete code can be found in this [Jupyter Notebook (IPYNB)](https://github.com/Zhanglab-abe/Crop-Yield-Prediction/blob/main/Crop_Yield_Prediction_XGBoost.ipynb). The request of the full dataset should be sent to the host of the [MLCAS2021 Crop Yield Prediction Challenge](https://eval.ai/web/challenges/challenge-page/1251/overview).*

# About the dataset
*Dataset request should be sent to the host of the [MLCAS2021 Crop Yield Prediction Challenge](https://eval.ai/web/challenges/challenge-page/1251/overview). The dataset folder should consist of two sub-folders: **Training**, **Test Inputs**. The training dataset comprises 93,028 performance records. The Training folder consists of the following files:*
- `inputs_weather_train.npy`: For each record, daily weather data - a total of 214 days spanning the crop growing season (defined April 1 through October 31). Daily weather records were compiled based on the nearest grid point from a gridded 30 km product. Each day is represented by the following **7 weather variables**:
  - `Average Direct Normal Irradiance (ADNI)`
  - `Average Precipitation (AP)`
  - `Average Relative Humidity (ARH)`
  - `Maximum Direct Normal Irradiance (MDNI)`
  - `Maximum Surface Temperature (MaxSur)`
  - `Minimum Surface Temperature (MinSur)`
  - `Average Surface Temperature (AvgSur)`
- `inputs_others_train.npy`:
  - `Maturity Group (MG)`
  - `Genotype ID`
  - `State`
  - `Year`
  - `Location` for each performance record
- `yield_train.npy`: Yearly crop yield value for each record

*The test dataset comprises 10,337 performance records. The Test Inputs folder consists of the following files:*
- `inputs_weather_test.npy`: Daily weather data for each performance record for a total of 214 days (time-steps). Each day is represented by **7 weather variables**: `ADNI`, `AP`, `ARH`, `MDNI`, `MaxSur`, `MinSur`, `AvgSur`.
- `inputs_others_test.npy`: `MG`, `Genotype ID`, `State`, `Year`, and `Location` for each performance record.

*The genotype clustering information is provided in `clusterID_genotype.npy`. The file contains **cluster ID** for each of the 5,839 genotypes. A completely connected pedigree for all lines with available parentage information was developed, resulting in the formation of a 5,839 x 5,839 correlation matrix. From the correlation matrix, the K-means algorithm was used for clustering.*
