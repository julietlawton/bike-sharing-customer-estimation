# Bike Sharing Prediction Models
Source code for user prediction models using neural networks and machine learning.

[UCI Bike Sharing Dataset](https://archive.ics.uci.edu/dataset/275/bike+sharing+dataset)

# EDA and Preprocessing
This section contains the code for exploratory data analysis and preprocessing. 
- Each categorical varaible is examined for unique values.
- To align with `hr`, we shift the varaibles `season`, `mnth`, and `weathersit` by `-1`.
- Categorical variables are then cast into the categorical dtype.
- Dropped `instant` which serves as the ID.
- Dropped `yr` which only tells us the year 2011 or 2012.
- Created a new `datetime` column which formats `dteday` and `hr` into a datetime dtype.
- Added a new column `casual_vs_registered` which takes the ratio of casual and registered users.
- Zero handling for `casual` and `registered` replaces 0 with 1.
- A Pandas profiling report is included in this section.
- Categorical features are one hot encoded.
- Distance correlations are generated for various continuous independent variables.
# Time Series Forecasting
This section will reference the Tensorflow [Time Series Tutorial](https://www.tensorflow.org/tutorials/structured_data/time_series) documentation.
- Data is split into 70% training, 20% validation, and 10% testing.
- Datasets are normalized in the training model and reverse normalized for the outputs.
- `WindowGenerator` defines the window size.
- `one_hour_window`, `discrete_window`, `continuous_window` is provided to test different windowed predictions.
- Tensorflow datasets are created for data splits and time series.
- All time series models have a 30 epoch limit with early stopping.
- Predictions are exported to `lstm_predictions.csv`
### Baseline Model
This model serves as a performance baseline for the LSTM model. Uses keras `MeanSquaredError` and `MeanAbsoluteError` to generate predictions.
### LSTM Model
This model uses a 16 unit `LSTM` and a 1 unit `Dense` layer.
# Casual User Prediction Model
Predicts casual user count taking in all dataset features.
- Uses a linear regression as the baseline model.
- Train test split with a test size of 0.2.
- Embeddings are created for categorical features.
- Stacks multiple layers including `Dense`, `BatchNormalization`, and `Activation`.
- Prediction data is exported to `causal_preds.csv`.
- Original dataset with hot encodeding and datetime is exported to `bike_sharing.csv`.
