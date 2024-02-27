# Bike Sharing Prediction Models

# EDA and Preprocessing
This section contains the code for exploratory data analysis and preprocessing. 
- Each categorical varaible is examined for unique values.
- To align with `hr`, we shift the varaibles `season`, `mnth`, and `weathersit` by `-1`.
- Categorical variables are then cast into the categorical dtype.
- Dropped `instant` which serves as the ID.
- Dropped `yr` which only tells us the year 2011 or 2012.
- Created a new `datetime` column which formats `dteday` and `hr` into a datetime dtype.
- A distribution of casual users, registered users, and all users was examined with a `plt` histogram.
- Added a new column `casual_vs_registered` which takes the ratio of casual and registered users.
# Time Series Forecasting

### Baseline Model

### LSTM Model

# Casual User Prediction Model
