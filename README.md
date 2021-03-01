# Project Zomboid Timeseries


# Project Goal

The goal of this project is to forecast review trends using the number of reviews for Project Zomboid, a Steam Game. The reason I selected this game is because of my familiarity of the game, as well as the well-documented lifespan of the game through dev blogs.

Another thing of note is that the game suddenly gained an increase in reviews in recent times, and as such I wanted to see if models could forecast future trends after the spike in popularity.

Link to Game: https://store.steampowered.com/app/108600/Project_Zomboid/

# Dataset

Data was gathered from Steam on [1/13/2021] using Steam API.

Link to repository for Steam Review Code: https://github.com/woctezuma/download-steam-reviews

A total of 33990 Steam reviews were obtained.


# Repository Contents

- Obtaining Reviews (steamapiscraper.ipynb): The process used to obtain the datasets in preparation for cleaning and EDA.
- Time Series (Time Series.ipynb): Exploratory Data Analysis applied to the datasets, proccessed, and forecast models were created.

# EDA

tbd

# Modeling

A baseline model was created using a Naive Forecast. 

### Performance Metric

With the original results, I will be looking at RMSE. RMSE is more sensitive to large errors than other evaluation metrics. MAE is not good here, as the average number of reviews per day is relatively low, thus the mean absolute error relative to the average review is relatively large, thus indicating poor accuracy.

### Models
Four different models were used to forecast review trends after separating the dataset for train and test. The date 1/7/2020 was selected because the year of 2020 yielded a spike in average reviews compared to previous years, and thus I wanted half the year of 2020 to aid in training the models. I want to see if any models could accurately predict future reviews given that a large majority of the lifespan of the game thus far has had noticeably lower average number of reviews.

## Non-Filtered Data

### Naive Forecast: 
- R2: -0.04364652356950027
- MSE: 564.1122448979592
- MAE: 11.122448979591837
- MAPE: 34.24892097861555
- RMSE: 23.751047237921092

### Prophet:
- R2: 0.24708421512042555
- MSE: 406.96634735567284
- MAE: 11.534701969750031
- MAPE: 44.53169378768569
- RMSE: 20.173406934766195

### XGBoost:
- R2: 0.6235531409606847
- MSE: 203.47720989970986
- MAE: 8.818258334179314
- MAPE: 30.725074742851348
- RMSE: 14.26454380271973

### Pmdarima:
- R2: -0.2458540094233741
- MSE: 673.4095176853627
- MAE: 19.712605874728695
- MAPE: 84.04734843302037
- RMSE: 25.95013521516531

### LSTM Network:
- R2: -1.617519874541979
- MSE: 1414.8229109628894
- MAE: 28.559460320871096
- MAPE: 109.85023899509261
- RMSE: 37.61413179860582


## Filtered Data

### Naive Forecast: 
- R2: -0.022196028116201916
- MSE: 109.69770408163265
- MAE: 7.85969387755102
- MAPE: 32.581425187657466
- RMSE: 10.473667174472972

### Prophet:
- R2: -0.13874712272895096
- MSE: 122.20546886994023
- MAE: 9.361287241080731
- MAPE: 44.41705405936208
- RMSE: 11.054658243018652


### XGBoost:
- R2: -1.0723830278131445
- MSE: 222.39927946873314
- MAE: 9.268972445507439
- MAPE: 35.46063322499003
- RMSE: 14.913057348133988

### Pmdarima:
- R2: 0.06979314156227223
- MSE: 502.79579079902936
- MAE: 12.167955694244535
- MAPE: 47.560921617702824
- RMSE: 22.42310841072284

### LSTM Network:
- R2: -4.9857413899727145
- MSE: 642.3641548642012
- MAE: 22.888852630722887
- MAPE: 102.47012686855392
- RMSE: 25.344903922962523

# Findings

### About the Models

tbd

### Conclusion

tbd


### Limitations:

- I am running these models on a MacBook Air with 1.1 Ghz Dual-Core Intel Core i3. Perhaps a stronger computer could be used or a cloud service like Amazon Web Services could be used to run models that I normally cannot.

- etc

### Future-Work

tbd


