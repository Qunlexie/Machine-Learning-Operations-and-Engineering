# Hotel Reservation Cancellation Prediction

This repository contains code for building an MLOPs pipeline for predicting hotel reservation cancellations using binary classification. The pipeline consists of preprocessing, model training, and prediction stages.

## Repository Structure

The repository has the following structure:

```
├── Model Store/               # Directory for storing trained models
├── Prediction Store/          # Directory for storing prediction outputs
├── data.csv                   # Example input data file
├── preprocessing_module.py    # Preprocessing module
├── training_module.py         # Training module
├── prediction_module.py       # Prediction module
├── pipeline_module.py         # Training and prediction pipeline module
└── README.md                  # Project README file
```

## Abstract

Binary classification is a fundamental problem in data science and machine learning. The objective of this project was to build an MLOPs pipeline for a model that predicts hotel reservation cancellations.

Here, we simulate an MLOPs workflow that supports the training and prediction pipeline, utilizing the tuned XGBoost model obtained from offline data science experimentation. The MLOPs pipeline consists of three stages: preprocessing (Imputer and Encoder) with adjustable feature parameters for training and prediction, training and evaluation with configurable threshold logic and evaluation metrics, and prediction on the entire dataset using the latest promoted model.

## Engineering

The code is organized into separate modules and classes to handle specific tasks within the pipeline. The folder structure emulates how the code would be organized in a GitHub repository. The main components of the pipeline are as follows:

### Preprocessing Pipeline

The preprocessing pipeline handles data loading, feature engineering, column dropping, and data preprocessing steps such as imputation and one-hot encoding. The `HotelBookingPreprocessor` class performs these tasks and provides methods to preprocess the data. It uses the `pandas` library for data manipulation and the scikit-learn library for preprocessing.

### Training Pipeline

The training pipeline includes a helper trainer module and a training module. The helper trainer module contains the `HotelBookingTrainer` class, which is responsible for building and training an XGBoost classifier model. It also handles model evaluation and model promotion based on a defined metric threshold. The `HotelBookingTrainingPipeline` class combines the preprocessing and training steps into a single pipeline, allowing easy execution of the training process.

### Prediction Pipeline

The prediction pipeline consists of the prediction module and the prediction pipeline module. The prediction module contains the `HotelBookingPredictionPipeline` class, which loads the latest promoted model and preprocesses the input data before making predictions. The predictions are saved to a file in the specified output directory. The `HotelBookingTrainingAndPredictionPipeline` class combines the training and prediction pipelines into a single pipeline for running the entire workflow.

## Usage

To use the MLOPs pipeline for hotel reservation cancellation prediction, follow the instructions below:

1. Clone this repository to your local machine.
2. Install the required dependencies listed in the `requirements.txt` file.
3. Prepare the input data in a CSV file and place it in the root directory or specify the path to the data file.
4. Configure the file paths for storing models, metrics, and predictions in the respective pipeline modules.
5. Execute the pipeline script or import the necessary classes to run the pipeline programmatically.

Please refer to the specific module documentation and function descriptions for further details on how to customize and utilize each pipeline component.

## Bonus Features

The pipeline includes bonus features to provide flexibility to data scientists. These features allow parameterization of the pipeline according to data scientist requirements:

- Arbitrary set of features can be passed into the training and prediction jobs.
- % threshold increase for model promotion can be parameterized.
- Evaluation metric used for model evaluation can be parameterized.

##