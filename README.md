# 🛠️ Predictive Maintenance using AI

This is my project on Predictive Maintenance using Machine Learning. The idea is simple — instead of waiting for a machine to break down, we use sensor data (like temperature, vibration, RPM, etc.) to predict if the machine is going to fail **before** it actually happens. This helps save time, money, and prevents accidents in factories.

I built this project using Python, Machine Learning, and a Streamlit web app so anyone can enter sensor values and get an instant prediction.

## 📌 What this project does

1. Takes sensor readings as input (Temperature, Vibration, RPM, Voltage, Current, Pressure)
2. Predicts the machine's status: **Healthy / Warning / Faulty**
3. Shows a **Failure Probability (%)**
4. Shows a **Risk Level**: Low / Medium / High
5. Gives a **Maintenance Recommendation** (what action to take)
6. Saves every prediction to a database so you can see history later
7. Has a dashboard with charts to see overall trends.

## 🧰 Tools & Technologies I used

- **Python** – main programming language
- **Google Colab** – for writing and testing the code
- **Pandas & NumPy** – for handling and cleaning the data
- **Matplotlib & Seaborn** – for making graphs during data analysis (EDA)
- **Scikit-learn** – for building the Machine Learning models
- **Plotly** – for interactive charts inside the web app
- **Joblib** – to save the trained model so I don't have to train it again and again
- **Streamlit** – to build the web app (frontend)
- **SQLite** – small database to store prediction history
- **Git & GitHub** – for version control and hosting the project

## 🤖 Machine Learning Models I compared

I didn't just use one model — I trained multiple models and compared their performance:

| Model | What it does |
|---|---|
| Logistic Regression | Simple baseline model |
| Decision Tree | Makes decisions using if-else type questions |
| **Random Forest** ✅ | Combines 200 decision trees and takes a majority vote — this is the model I finally used |
| SVM | Draws the best boundary line between classes |
| XGBoost (optional) | Builds trees one after another to fix previous mistakes |

I picked **Random Forest** as the final model because it's more accurate and doesn't easily overfit compared to a single Decision Tree.



## 📁 Project Structure

```
predictive_maintenance/
│
├── generate_dataset.py     -> creates a sample dataset (if real dataset not available)
├── train_model.py          -> cleans data, does EDA, trains models, saves the best one
├── app.py                  -> the Streamlit web app
├── requirements.txt        -> list of libraries needed
├── README.md                -> this file
│
├── data/
│   └── machine_data.csv    -> dataset used for training
│
├── models/                 -> saved trained model, scaler, encoders (as .pkl files)
│
└── outputs/
    └── eda/                -> graphs generated during data analysis
```

---

## 🚀 How to run this project

### Step 1: Clone this repo
```bash
git clone https://github.com/<your-username>/predictive-maintenance-ai.git
cd predictive-maintenance-ai
```

### Step 2: Install required libraries
```bash
pip install -r requirements.txt
```

### Step 3: Get the dataset
Either use the real dataset from Kaggle (Machine Fault Detection Dataset) and place it in `data/machine_data.csv`, OR just run this to generate a sample dataset:
```bash
python generate_dataset.py
```

### Step 4: Train the model
```bash
python train_model.py
```
This will clean the data, generate graphs, train all the models, compare them, and save the best model.

### Step 5: Run the web app
```bash
streamlit run app.py
```
### LIVE PROJECT WORKING LINK:-https://predictive-maintenance-system-based-ai-2tzqpmxzupchkquv53akif.streamlit.app/

---

## 📊 Input Features

| Feature | Meaning |
|---|---|
| Machine_Type | Type of machine (Motor, Pump, Compressor, Turbine) |
| Temperature | In °C |
| Vibration | In mm/s |
| RPM | Rotational speed |
| Voltage | In Volts |
| Current | In Amperes |
| Pressure | In bar |

## 🎯 Output

- Machine Status: **Healthy / Warning / Faulty**
- Failure Probability: **e.g. 72%**
- Risk Level: **Low / Medium / High**
- Maintenance Recommendation (what to do next)

---

## 🖥️ App Pages

1. **Predict** – enter sensor values and get an instant prediction
2. **Prediction History** – see all past predictions (stored in SQLite)
3. **Dashboard** – graphs and charts showing overall trends
4. **About** – info about the project

---

## 📈 Model Evaluation

I evaluated all models using:
- Accuracy
- Precision
- Recall
- F1-Score
- Confusion Matrix

Random Forest performed the best overall and was saved for use in the app.



## 🙋‍♂️ What I learned from this project

- How to clean and analyze real-world type data
- How to train and compare multiple Machine Learning models
- How to save and reuse a trained model using Joblib
- How to build a simple web app using Streamlit
- How to connect an app to a database (SQLite)
- How to use Git and GitHub for a full project
- How to deploy a Machine Learning project online


## 🧑‍💻 Author

Made by Dhairya Srivastava as a project on Predictive Maintenance using AI.
