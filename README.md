# Heart Disease Prediction Project

This project focuses on predicting heart disease using machine learning models. It includes data cleaning, exploratory data analysis (EDA), feature importance analysis, model selection, parameter tuning, and deployment via a web service. The solution is designed for effective containerization and deployment.

## Table of Contents
1. [Project Overview](#project-overview)
2. [Directory Structure](#directory-structure)
3. [Problem Description](#problem-description)
4. [Installation and Setup](#installation-and-setup)
5. [Running the Project](#running-the-project)
6. [Model Deployment](#model-deployment)
7. [Docker Containerization](#docker-containerization)
8. [Testing the Application](#testing-the-application)
9. [Contributing](#contributing)
10. [License](#license)

---

## Project Overview

Heart disease remains one of the leading causes of death globally. This project leverages machine learning techniques to predict the likelihood of heart disease based on patient data. 

Key features include:
- Data preparation and cleaning.
- Exploratory Data Analysis (EDA) to uncover patterns and relationships.
- Model training, evaluation, and parameter optimization.
- Deployment via Flask and containerization using Docker for scalable web service hosting.

---

## Directory Structure

```
heart-disease-prediction/
│
├── data/                          # Contains the dataset
├── images/                        # Illustrations and deployment screenshots
├── midterm_project.ipynb          # Jupyter Notebook with data preparation and analysis
├── train.py                       # Script for training and saving the model
├── predict.py                     # Web service for serving the model
├── no_app_predict_test.py         # Test script for direct model testing
├── predict_test.py                # Script for testing the web service
├── Pipfile                        # Dependencies for pipenv
├── Pipfile.lock                   # Locked versions of dependencies
├── Dockerfile                     # Docker configuration for containerization
└── README.md                      # Project description and instructions
```

---

## Problem Description

Cardiovascular diseases are a major global health challenge. This project aims to use machine learning to:
- Identify individuals at risk of heart disease.
- Provide a tool for healthcare professionals to make informed decisions.
- Deliver an easily deployable service for real-world use cases.

The dataset contains anonymized patient records with various features, such as age, cholesterol levels, and blood pressure, which are used to predict the risk of heart disease.

---

## Installation and Setup

This project uses **Python 3.11** and requires an Ubuntu distribution with **WSL 2.0**. 

### 1. Clone the Repository
```bash
git clone https://github.com/your-username/heart-disease-prediction.git
cd heart-disease-prediction
```

### 2. Install Dependencies
Use `pipenv` to manage dependencies:
```bash
pip install pipenv
pipenv install flask scikit-learn==1.5.1 gunicorn
```

### 3. Create and Activate the Environment
```bash
pipenv shell
```

---

## Running the Project

### 1. Training the Model
Train the model and save it as a binary file:
```bash
python train.py
```

### 2. Running the Web Service
Start the Flask application:
```bash
gunicorn --bind 0.0.0.0:9696 predict:app
```

### 3. Testing the Web Service
Send a test request using `predict_test.py`:
```bash
python predict_test.py
```

---

## Model Deployment

The model is deployed using Flask. Follow these steps:
1. Serve the app using Flask and test its functionality:
   ```bash
   python predict_test.py
   ```
2. Transition to containerized deployment with Docker.

---

## Docker Containerization

### 1. Build the Docker Image
Create a Docker image for the project:
```bash
docker build -t heart-prediction-app .
```

### 2. Run the Docker Container
Run the image and map the port:
```bash
docker run -it --rm -p 9696:9696 heart-prediction-app
```

### 3. Test the Application
Send a request to the service using:
```bash
python predict_test.py
```

---

## Testing the Application

You can test the model without the Flask app using:
```bash
python no_app_predict_test.py
```

Alternatively, send test requests to the Flask web service:
```bash
python predict_test.py
```

---

## Contributing

We welcome contributions to enhance this project. Please:
- Fork the repository.
- Create a new branch for your feature or bug fix.
- Submit a pull request with a detailed description of your changes.

---

## License

This project is licensed under the [MIT License](LICENSE).

---

Let me know if you'd like further refinements or additional sections!
