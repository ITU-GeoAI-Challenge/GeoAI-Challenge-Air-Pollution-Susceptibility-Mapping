# GeoAI-Challenge-Air-Pollution-Susceptibility-Mapping
Submission by Isaac Oluwafemi Ogunniyi (zindi username: isaacOluwafemiOg) for the ITU GeoAI Air Pollution Susceptibility Mapping challenge

This solution consist of four files:
- 3 data files (all from the data provided as part of the competition):
    - 'Train.csv' which contains meteorological and spatial data for geometries
together with their classification represented by the ‘aqi’ values.
    - 'Test.csv' contains the data of locations for testing the performance of the
model
    - ‘SampleSubmission.csv’ to guide the creation of the submission file
- A Jupyter notebook named 'AirPollution_Susceptibility.ipynb' containing the code for
handling data, training model and predicting the air pollution susceptibility of the test
locations.
## The environment
The Jupyter notebook runs in a python environment. For a Google Colab CPU runtime type,
it lasts under 10 minutes.
No paid subscriptions or resources were used.
## The Jupyter Notebook
* This notebook takes input of all 3 data files mentioned previously and outputs
'Submission.csv'.
* To run the notebook the 'data_path'' variable must contain the path to the directory
containing all the data files mentioned previously.
* The notebook contains python code and the whole code runs on Google colab lasting
for under 10 minutes.
* The General Overview of the Notebook is as follows:
 1. Importing Relevant libraries
pandas (1.5.3), numpy (1.23.5), scikit-learn (1.2.2), scipy(1.11.3)
 2. Reading Data
 3. Engineering Features
The features fed into the model are 62 and fall into 2 categories:
    - Features for the geometry in the current year for which prediction is
being made. These features such as ‘ssn_1.0’ and ‘ssn_2.0’ which are
the one-hot encoded versions of the ‘season’ column
    - Features from the previous year’s data for the same geometry whose
‘aqi’ is to be forecasted. It must be noted that the ‘aqi’ value for the
previous year is renamed as ‘aqi_y’ so it is not confused (in the case
of the training set) for the ‘aqi’ to be predicted.
 4. Developing Pipelines and training models
     - Pipeline involved scaling (standardScaler), selecting best features
(SelectKBest) and then fitting a RandomForestClassifier model.
     - The model's hyperparameters were tuned using the RandomizedsearchCV
 5. Predicting and preparing submission
    - Predictions are made on the data imported from 'Test.csv' which has been
transformed to include the same features as the train data.
    - The final predictions are exported to 'Submission.csv' in the same directory as
the jupyter notebook.
