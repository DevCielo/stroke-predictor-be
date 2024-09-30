# Stroke Predictor Web App - Backend

## Table of Contents
1. [Project Description](#project-description)
2. [Frontend](#frontend)
3. [Features](#features)
4. [Technologies Used](#technologies-used)
5. [Machine Learning Model](#machine-learning-model)
6. [API Endpoints](#api-endpoints)
7. [Installation](#installation)
8. [Usage](#usage)
9. [Contributing](#contributing)
10. [License](#license)

## Project Description
The backend of the **Stroke Predictor Web App** is built using Flask and serves as the machine learning model’s API provider. It accepts user input from the frontend, processes the data using a pre-trained model, and returns the stroke prediction result.  I created this project to learn how to deploy machine learning models on a web app using Flask.

## Frontend
Frontend can be found at: https://github.com/DevCielo/stroke-predictor-fe/tree/main

## Features
- Machine Learning model trained to predict stroke risk.
- REST API to accept user data and return predictions.
- Data processing and validation for better model performance.
- Easy integration with the React frontend.

## Technologies Used
- Flask
- Python
- Scikit-learn (for the ML model)
- Joblib (to load the trained model)
- Pandas (for data processing)
- Flask-CORS (for enabling cross-origin requests)

## Machine Learning Model
- The stroke prediction model was trained on the [Stroke Prediction Dataset](https://www.kaggle.com/fedesoriano/stroke-prediction-dataset).
- The model is saved in `.joblib` format and loaded into the Flask app at runtime.
- The model predicts the probability of stroke based on user input like age, hypertension, heart disease, etc.

## API Endpoints

- `POST /predict`: Accepts medical data in JSON format and returns the stroke prediction result.

    **Sample request**:

    ```json
    {
        "age": 45,
        "hypertension": 0,
        "heart_disease": 1,
        "avg_glucose_level": 110.12,
        "bmi": 24.3,
        "gender": "Female"
    }
    ```

    **Sample response**:

    ```json
    {
        "prediction": "high risk"
    }
    ```

## Installation

1. Clone the repository:

    ```bash
    git clone https://github.com/DevCielo/stroke-predictor-web-app-be
    cd stroke-predictor-web-app-backend
    ```

2. Create a virtual environment:

    ```bash
    python3 -m venv venv
    source venv/bin/activate
    ```

3. Install dependencies:

    ```bash
    pip install -r requirements.txt
    ```

4. Run the Flask app:

    ```bash
    flask run
    ```

5. The API will be available at `http://localhost:5001`.

6. To see in usage, run frontend simultaneously.

## Usage
1. Send a `POST` request to `http://localhost:5001/predict` with medical data.
2. Receive a JSON response with the stroke prediction (e.g., "low risk" or "high risk").

## Contributing
Feel free to contribute by forking the repository, making a branch, and submitting a pull request. Report any issues you find.

## License
This project is free to use for your own personal or commercial needs.
