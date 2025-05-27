# Machine Learning ETL Pipeline for NASA Airfoil Noise Prediction

## Project Overview

You are a data engineer at an aeronautics consulting company specializing in designing airfoils for planes and sports cars. The company relies on efficient data pipelines and machine learning to predict airfoil noise levels, which helps optimize airfoil design.

This project demonstrates a complete ML ETL pipeline on a modified version of the NASA Airfoil Self Noise dataset. The goal is to clean the data, build a predictive model for the noise level, evaluate the model, and persist it for production use.

---

## Dataset

- Original Dataset: [NASA Airfoil Self Noise dataset](https://archive.ics.uci.edu/dataset/291/airfoil+self+noise)
- Modified Dataset (used in this project): [NASA_airfoil_noise_raw.csv](https://cf-courses-data.s3.us.cloud-object-storage.appdomain.cloud/IBMSkillsNetwork-BD0231EN-Coursera/datasets/NASA_airfoil_noise_raw.csv)
- Dataset license: Creative Commons Attribution 4.0 International (CC BY 4.0)

---

## Project Structure

### Part 1: Perform ETL Activity

1. Load CSV dataset into Spark DataFrame.
2. Remove duplicate rows.
3. Drop rows containing null values.
4. Rename the target column from `SoundLevel` to `SoundLevelDecibels`.
5. Save the cleaned data as a Parquet file (`NASA_airfoil_noise_cleaned.parquet`).

### Part 2: Create a Machine Learning Pipeline

1. Load cleaned data from Parquet file.
2. Assemble feature columns into a vector using `VectorAssembler`.
3. Scale features using `StandardScaler`.
4. Create a `LinearRegression` model to predict `SoundLevelDecibels`.
5. Build a Spark ML Pipeline consisting of the above stages.
6. Split data into training and testing sets.
7. Fit the pipeline to the training data.

### Part 3: Evaluate the Model

1. Use the trained pipeline model to predict on the test set.
2. Evaluate model performance using:
   - Mean Squared Error (MSE)
   - Mean Absolute Error (MAE)
   - R-Squared (R²)
3. Print model intercept and metrics.

### Part 4: Persist the Model

1. Save the trained pipeline model to disk (`Final_Project` directory).
2. Load the saved model back from disk.
3. Make predictions with the loaded model to verify correctness.
4. Print model coefficients for each feature.

---

## Environment Setup

### Required Libraries

```bash
pip install pyspark==3.1.2 findspark
