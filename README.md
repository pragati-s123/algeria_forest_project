# Algeria Forest Fire Prediction

A Flask web app that predicts the Fire Weather Index (FWI) for Algerian forest regions using a Ridge Regression model, based on meteorological and fire behavior indices.

🔗 **Live Demo:** https://algeria-forest-project.onrender.com/

## Overview

This project uses the [Algerian Forest Fires dataset](https://archive.ics.uci.edu/dataset/547/algerian+forest+fires+dataset) to train a Ridge Regression model that predicts fire risk based on weather and fire index inputs. The trained model is served through a Flask web interface where users can input values and get a real-time prediction.

## Features

- Real-time FWI prediction from user-input weather data
- Ridge Regression model with feature scaling (StandardScaler)
- Simple web form interface built with Flask + HTML templates
- Deployed and publicly accessible

## Input Parameters

| Parameter | Description |
|---|---|
| Temperature | Max temperature (°C) |
| RH | Relative Humidity (%) |
| Ws | Wind Speed (km/h) |
| Rain | Rainfall (mm) |
| FFMC | Fine Fuel Moisture Code |
| DMC | Duff Moisture Code |
| ISI | Initial Spread Index |
| Classes | Fire occurrence class |
| Region | Region indicator |

## Tech Stack

- **Backend:** Flask
- **ML:** scikit-learn (Ridge Regression, StandardScaler)
- **Data handling:** NumPy, Pandas
- **Deployment:** Render

## Project Structure

```
algeria_forest_project/
├── application.py        # Flask app entry point
├── requirements.txt
├── models/
│   ├── ridge.pkl          # Trained Ridge Regression model
│   └── scaler.pkl         # Fitted StandardScaler
├── templates/
│   ├── index.html
│   └── home.html
├── notebooks/             # EDA and model training notebooks
├── dataset/                # Source dataset
└── .ebextensions/          # AWS Elastic Beanstalk config (legacy)
```

## Run Locally

```bash
git clone https://github.com/pragati-s123/algeria_forest_project.git
cd algeria_forest_project
pip install -r requirements.txt
python application.py
```

Then open `http://127.0.0.1:5000` in your browser.

## Model

The model is a **Ridge Regression** trained on scaled input features to predict the Fire Weather Index. Both the model and the scaler are serialized with `pickle` and loaded at app startup.

## Author

**Pragati Sharma**
