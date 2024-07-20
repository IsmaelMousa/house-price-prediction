# House Price Prediction

Predicting house prices using machine learning models.

## Overview

The primary goal is to build and evaluate various models to predict house prices based on the housing price dataset.

The models used include:
- **Linear Regression**
- **Lasso (L1)**
- **Ridge (L2)**
- **Random Forest Regression**

## Dataset

The dataset used is sourced from Kaggle and includes various features related to house prices.

## Workflow

1. **Reading the Data**:
   - Load and inspect the dataset.
   - The raw data is located in the `data` directory under the name `housing.csv`.


2. **Exploratory Data Analysis (EDA)**:
   - Explore the data size.
   - Explore the data types and check for empty values.
   - Analyze the data by visualizing its features.
   - Analyze the correlation between the features.


3. **Data Preprocessing**:
   - Convert `lat` & `long` coordinates to `city` using the **LocationIQ** API.
   - Replace `Unknown` city values with the nearest city using **NearestNeighbors**, based on `lat` & `long` coordinates.
   - Remove unnecessary features.
   - Detect and handle outliers using **IQR** & **KNN**.
   - Encode categorical features using **One-Hot Encoding**.
   - Split the dataset into `inputs` & `outputs`, then split it into `train` & `test` sets.
   - Ensure the data is ready for training and evaluation.


4. **Model Training & Evaluation**:
   - Train multiple models using a **Pipeline**:
     - Linear Regression
     - Lasso (L1)
     - Ridge (L2)
     - Random Forest Regressor
   - Evaluate the performance of each model using the **RMSE** loss function and **R²** score.
   - Compare predicted values with actual values.


5. **Save & Load the Models**:
   - Save the models to `.pkl` files inside the `models` directory.
   - Load the models and make predictions.

## Dependencies

- **`pandas`**: Data manipulation and analysis.
- **`numpy`**: Numerical operations on arrays.
- **`scikit-learn`**: Machine learning algorithms and tools.
- **`matplotlib`**: Plotting and visualization.
- **`seaborn`**: Data visualization.
- **`requests`**: Sending HTTP requests (used for LocationIQ API).

## Try it!

To start using this project, follow the steps below:

1. Clone this repository to your local machine:

    ```zsh
    git clone git@github.com:IsmaelMousa/house-price-prediction.git
    ```

2. Navigate to the **house-price-prediction** directory:

    ```zsh
    cd house-price-prediction
    ```

3. Set up a virtual environment:

    ```zsh
    python3 -m venv .venv
    ```

4. Activate the virtual environment:

    ```zsh
    source .venv/bin/activate
    ```

5. Install the required dependencies:

    ```zsh
    pip install -r requirements.txt
    ```

6. Run the Jupyter Notebook:

    ```zsh
    jupyter-notebook
    ```

>[!IMPORTANT]
>
> For reverse geocoding, the [LocationIQ](https://locationiq.com) API is used. If you wish to perform reverse geocoding, sign up [here](https://my.locationiq.com/register) and replace the placeholder with your token:
> ```
> key = "YOUR_LOCATIONIQ_API_KEY"
> ```
>
> If you don't want to try the reverse geocoding, you can skip this step.

## Results

The results include performance metrics for each model and comparisons of predicted versus actual values.

Detailed analysis and model performance summaries are provided in the [main.ipynb](main.ipynb).

## Acknowledgments

The dataset used in this project is available on Kaggle: [House Prices](https://www.kaggle.com/datasets/sukhmandeepsinghbrar/housing-price-dataset).
