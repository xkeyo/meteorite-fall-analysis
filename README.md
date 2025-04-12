# Data Analytics - Mini Project Proposal
## Ihana Fahmy & Pratham Patel

### <center>Meteorites Dataset: _Where will the next likely impact zone be?_</center>

### Project Overview
This project used the Meteorite Landings on Earth dataset which has over 34,500+ records. It is compiled by the Meteoritical Society and hosted on NASA’s Open Data Portal. This project aims to predict the next meteorite landing based on its mass, classification and geolocation. 

### The Columns Included:
- name: The official name of the meteorite.
- id: A unique identifier for each meteorite.
- nametype: Indicates whether the meteorite is: Valid (Most meteorites) or Relict (Highly weathered meteorites).
- recclass: The classification of the meteorite based on its composition and structure.
- mass (g): The recorded mass of the meteorite in grams
- fall: Specifies whether the meteorite: Fell (Observed falling and later recovered) or Found (Discovered without being observed falling).
- year: The year the meteorite was observed or discovered.
- reclat: The latitude coordinates of the meteorite's location.
- reclong: The longitude coordinates of the meteorite's location.
- GeoLocation: A structured representation of the meteorite’s geographic location in (latitude, longitude) format.

### Models, Accuracy/Precision Checks & Hyperparameters
As the goal of this project is to find geolocations which are continuous values, regression models need to be used. The models that are going to be used are: XGBoost and Random Forest Regression.
- XGBoost: Extreme Gradient Boosting is a machine learning algorithm based on gradient boosting. It builds multiple decision trees and improves mistakes from previous trees. It is efficient for large datasets, ours being over 30,000+, can work with missing data points, and can find non-linear relationships between features and targets.

- Random Forest Regression: Random Forest is an ensemble machine learning algorithm that builds multiple independent decision trees and averages their outputs to make predictions. It is efficient when a dataset contains many irrelevant features, has a lower risk of overfitting, and requires less tuning than XGBoost. 

For the testing and training, hyperparameters are going to be used to enhance the model training. The hyperparameter tuning will be used with: GridSearchCV.
- RandomizedSearchCV: RandomizedSearchCV uses randomized search on hyperparameters for both models to minimize and optimize the mean squared error (MSE). It is a powerful tool in scikit-learn and is very useful for hyperparameter tuning as it uses a random search by testing a random subset of hyperparameter combinations and selects the best one. This allows us to find the most relevant features to help with the model’s performance.

To choose the best model between the two and avoid overfitting, K-Fold Cross Validation will be used. Using this evaluation function, regression performance metrics such as Mean Squared Error (MSE), Mean Absolute Error (MAE), and R2 Score will be used for each fold.
- K-Fold Cross Validation: K-Fold Cross Validation is an evaluation technique that assess the model’s performance on unseen data. It splits the data into k number of training and testing sets known as folds. It performs training on all the subsets except for one and tests the last one. It does this k times each time with a different subset to test on. It finally computes the average performance on all folds. This prevents overfitting and is more reliable for accuracy measurement as it is tested multiple times.
