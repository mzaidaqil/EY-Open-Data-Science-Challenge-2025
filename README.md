# Urban Heat Island (UHI) Index Prediction

## Project Overview
This project aims to predict the Urban Heat Island (UHI) Index for various locations in New York City using satellite imagery data and machine learning techniques.

## Data Sources
1. **Satellite Imagery Data:** Extracted from Landsat 8 satellite images, including bands such as blue, green, red, near-infrared (nir08), shortwave infrared (swir16 and swir22), and thermal infrared (lwir11).
2. **Ground Truth Data:** UHI Index values for various locations in New York City.

## Features Used
- **Blue Band**
- **Green Band**
- **Red Band**
- **Near-Infrared (nir08) Band**
- **Shortwave Infrared (swir16 and swir22) Bands**
- **Thermal Infrared (lwir11) Band**
- **Normalized Difference Vegetation Index (NDVI)**: Calculated using the formula `(nir08 - red) / (nir08 + red)`

## Methodology
1. **Data Preprocessing:**
   - Filtered the dataset to include only valid NYC coordinates.
   - Removed duplicate rows and outliers based on the UHI Index.
   - Extracted satellite band values from GeoTIFF files based on the coordinates from the CSV file.
   - Calculated NDVI and handled division by zero by replacing infinities with NaN and filling NaNs with 0.

2. **Feature Engineering:**
   - Combined the original data with the mapped satellite data.
   - Included all relevant bands and the calculated NDVI in the final dataset.

3. **Model Training:**
   - Selected relevant bands and NDVI as features for model training.
   - Defined the target variable as the UHI Index.
   - Split the data into training and testing sets.
   - Trained a RandomForestRegressor model on the training data.
   - Evaluated the model's performance on the test data.

## Results
- The model was trained and evaluated, achieving an accuracy score on the test data.

## Submission
- The `submission.csv` file contains the predicted UHI Index values for various locations in New York City. The columns in the file are:
  - **Longitude:** Longitude of the location.
  - **Latitude:** Latitude of the location.
  - **UHI Index:** Predicted UHI Index value for the location.

## Instructions
- Upload the `submission.csv` file on the [EY Challenge Platform](https://challenge.ey.com) to get the score generated on the scoreboard.

  <img src="EY_score.jpeg" alt="Screenshot" width="800">

