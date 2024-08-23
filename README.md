## I-GUIDE-Team-4
# GeoAI Applications to Predict Field Scale Actual Evapotranspiration

# Python Files

## `ETa_Modeling.ipynb`

This Jupyter notebook is dedicated to modeling actual evapotranspiration (ETa) using a combination of remote sensing data and machine learning techniques. The notebook covers the following key areas:

### Main Contents:

- **Data Merging, Interpolation, Cleaning, and Exploratory Data Analysis (EDA):**
  - Merging datasets on common attributes, applying linear interpolation to fill missing values, and dropping remaining NaN values.
  - Conducting visualizations and statistical analysis to understand data distributions, trends, and correlations.
  - Creating or transforming features to enhance model performance.

- **Machine Learning Modeling:**
  - Developing and training several machine learning models, including Support Vector Machine (SVM), Random Forest (RF), Gradient Boosting Machine (GBM), and 1D Convolutional Neural Network (1D-CNN) to predict ETa.

- **Feature Importance Analysis:**
  - Using techniques like permutation importance and SHAP values to assess the significance of different features in the models.

- **Model Evaluation:**
  - Evaluating the models' performance using appropriate metrics, with visualizations to illustrate their accuracy.

## `DL_Models.ipynb`

This Jupyter notebook focuses on developing deep learning models for predicting actual evapotranspiration (ETa) using a combination of remote sensing data and meteorological observations. The notebook includes the following key sections:

### Main Contents:

- **Data Merging and Preprocessing:**
  - Merging ETa data with vegetation and thermal indices based on attributes like date and site name, followed by data cleaning and preprocessing to prepare the dataset for modeling.

- **Deep Learning Model Development:**
  - Developing and training various deep learning models, particularly neural networks, with setups including model architectures, layers, activation functions, and optimization parameters.

- **Model Training and Evaluation:**
  - Training the models on the prepared datasets and evaluating their performance using metrics such as mean squared error (MSE) and R-squared (R²). The notebook also includes plots of training history and loss curves.

## `Comparison_of_OpenETa_and_ETa_from_AmeriFlux_Tower.ipynb`

This Jupyter notebook compares actual evapotranspiration (ETa) data from AmeriFlux tower sites with ETa estimates derived from the OpenETa platform. It includes the following main contents:

### Main Contents:

- **Data Filtering and Preprocessing:**
  - Filtering AmeriFlux data to include only dates from 2019 to 2021, ensuring consistent comparison with the OpenETa dataset.

- **Data Merging:**
  - Merging the filtered AmeriFlux data with OpenETa data based on the common date attribute.

- **Statistical Analysis:**
  - Calculating various statistical metrics like mean absolute error (MAE) and root mean squared error (RMSE) to quantify the differences between ETa values from AmeriFlux and OpenETa.

- **Visualization:**
  - Generating scatter plots and time series plots to visually compare ETa values from both datasets, identifying patterns and discrepancies.

- **Statistical Tests:**
  - Performing statistical tests, such as paired t-tests or Wilcoxon signed-rank tests, to evaluate significant differences between the ETa values from the two datasets.

# Google Earth Engine Files

## `MODIS_FPAR_LAI.txt`

This Google Earth Engine (GEE) script extracts Fraction of Photosynthetically Active Radiation (FPAR) and Leaf Area Index (LAI) data from the MODIS MCD15A3H dataset for predefined locations. The script:

- Defines a date range from January 1, 2000, to December 31, 2023.
- Applies a scaling function to convert raw MODIS data into meaningful FPAR and LAI values.
- Maps this function across the image collection and extracts the corresponding values for each point location specified in the shapefile.
- Aggregates the data and exports it to a CSV file for further analysis.

## `MODIS_LST.txt`

This script extracts Land Surface Temperature (LST) data, both day and night, from the MODIS MOD11A2 dataset for specific locations. The script:

- Sets a date range from January 1, 2000, to December 31, 2023.
- Selects relevant LST bands from the dataset and scales the raw data into meaningful temperature values.
- Maps the scaling function across the image collection and retrieves day and night LST values for each location in the shapefile.
- Compiles the data into a feature collection and exports the results to a CSV file.

## `MODIS_NDVI_EVI.txt`

This GEE script focuses on extracting the Normalized Difference Vegetation Index (NDVI) and Enhanced Vegetation Index (EVI) from the MODIS MOD09A1 dataset for defined locations. The script:

- Filters the dataset for a specified period from January 1, 2000, to December 31, 2023.
- Selects the necessary spectral bands for NDVI and EVI calculations.
- Computes NDVI using the normalized difference of near-infrared and red bands and calculates EVI using a specific formula that accounts for atmospheric conditions.
- Extracts these vegetation indices for each point in the shapefile, aggregates the data, and exports the output to a CSV file for detailed vegetation analysis over time and across different sites.
