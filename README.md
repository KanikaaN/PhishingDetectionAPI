# PhishingDetectionAPI


## Overview

This project focuses on detecting phishing websites using machine learning models. It involves data preprocessing, model training, evaluation, and deployment of a phishing detection model as a web service. The model is deployed using Flask and Docker, and its functionality is verified using Postman.

## Repository Structure

```
PhishingDetectionAPI/
│
├── test/
│   ├── legitimate POST Request.txt               # POST Request URL with features of Legitimate input
│   ├── legitimate POST Request.txt               # POST Request URL with features of Phishing input
│   └── Docker Pull and run command.txt           # Commands to access and test docker image 
│
├── Testing models/
│   ├── PhishingDetectionModels.ipynb             # Jupyter notebook for model evaluation, analysis and saving best model
│   ├── Dataset_phishing.csv                      # Kaggle Dataset for training and testing model
│   └── xgb_model.pkl                             # Pickled XGBoost model
│
├── xgb_model.pkl                  # Pickled XGBoost model
├── Dockerfile                         # Dockerfile for containerizing the Flask application
├── requirements.txt                   # Python dependencies
├── README.md                          # This README file
└── .gitignore                         # Git ignore file to exclude unnecessary files
```

## Getting Started

To get started with the project, follow the instructions below:

### Prerequisites

- Python 3.x
- Docker (for containerization)
- Postman (for testing the API)

### Installation

1. **Clone the repository:**

   ```bash
   git clone https://github.com/KanikaaN/PhishingDetectionAPI.git
   cd PhishingDetectionAPI
   ```

2. **Install Python dependencies:**

   ```bash
   pip install -r requirements.txt
   ```

### Running the Jupyter Notebook

1. Launch Jupyter Notebook:

   ```bash
   jupyter notebook
   ```

2. Open the `Testing Models/PhishingDetectionModelsn.ipynb` file to view and run the notebook for model evaluation. The trained model will be saved as `xgb_model.pkl` in the same directory.

### Deploying the Flask API

1. Build the Docker image:

   ```bash
   docker build -t phishing-detection-api .
   ```

2. Run the Docker container:

   ```bash
   docker run -p 5000:5000 phishing-detection-api
   ```

3. The Flask API will be available at `http://localhost:5000/predict`.

### Testing the API

1. Open Postman and send a POST request to `http://localhost:5000/predict` with JSON data representing website features.

2. Verify the responses to ensure the API is working as expected.

