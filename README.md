# Student Performance Prediction 🎓📊

![Python](https://img.shields.io/badge/Python-3.8+-blue.svg)
![Flask](https://img.shields.io/badge/Flask-Web%20Framework-lightgrey.svg)
![Machine Learning](https://img.shields.io/badge/Machine%20Learning-Scikit--Learn-orange.svg)
![Status](https://img.shields.io/badge/Status-Live-brightgreen.svg)

**🚀 Live Application:** [Student Performance Predictor](https://student-performance-prediction-b1a6.onrender.com)

This is an End-to-End Machine Learning project focused on predicting student math performance based on their demographic information, parental level of education, lunch plan, and test preparation score. It includes a complete data pipeline (ingestion, transformation, modeling), robust logging & exception handling, and a web interface for making real-time predictions.

## 🌟 Live Demo
The application is currently deployed and live on Render! You can interact with the predictive model directly without setting up the project locally.

👉 **[Try the Live Web App Here](https://student-performance-prediction-b1a6.onrender.com)**

## 🚀 Web Server Code
The application exposes a web interface created with **Flask**. 
You can find the core web server logic in these files:
- 🔗 [`app.py`](./app.py): The main Flask server application which defines the routing for the home page (`/`) and the prediction endpoint (`/predictdata`).
- 🔗 [`application.py`](./application.py): Specifically configured for cloud deployments such as AWS Elastic Beanstalk (which looks for `application.py` by default).

## 🛠️ Project Architecture 
The project follows a standard and modular machine learning pipeline structure:

```text
ML_Project/
├── app.py & application.py        # 🌐 Web application entry points
├── src/                           # 🧠 Source code for ML pipelines
│   ├── components/                # Modular scripts for ML stages 
│   │   ├── data_ingestion.py      # Reads data and prepares train/test splits
│   │   ├── data_transformation.py # Preprocessing, scaling, encodings
│   │   └── model_trainer.py       # Trains multiple models and saves the best one
│   ├── pipeline/                  # Prediction and Training pipelines
│   │   └── predict_pipeline.py    # Used by the web app to predict on new data
│   ├── logger.py                  # 📝 Custom logging configuration
│   ├── exception.py               # ⚠️ Custom exception handling
│   └── utils.py                   # 🧰 Utility helper functions (e.g., save objects)
├── templates/                     # 🎨 HTML templates (home.html, index.html)
├── artifacts/                     # 📦 Model, preprocessor, and datasets saved here
├── notebook/                      # 📓 Jupyter notebooks for EDA and Model training
├── requirements.txt               # 📜 Python dependencies
└── setup.py                       # 🛠️ Script to make `src` a local package
```

## ⚙️ Tech Stack Used
* **Backend Framework:** Flask
* **Machine Learning:** Scikit-Learn, CatBoost, XGBoost
* **Data Processing:** Pandas, NumPy
* **Visualization:** Seaborn, Matplotlib
* **Serialization:** dill
* **Cloud Deployment:** Render / AWS Elastic Beanstalk

## 📥 How to Run Locally

1. **Clone the repository:**
   ```bash
   git clone <your-repo-link>
   cd ML_Project
   ```

2. **Create a virtual environment:**
   ```bash
   python -m venv venv
   # On Windows Activate:
   venv\Scripts\activate
   # On Mac/Linux Activate:
   source venv/bin/activate
   ```

3. **Install the required dependencies:**
   ```bash
   pip install -r requirements.txt
   ```

4. **Run the Flask application:**
   ```bash
   python app.py
   ```
   *Alternatively, run `python application.py`*

5. **Access the application:**
   Open your browser and navigate to: [http://127.0.0.1:5000/](http://127.0.0.1:5000/)

## 📝 Usage
Whether using the **[Live Demo](https://student-performance-prediction-b1a6.onrender.com)** or running locally, simply navigate to the `/predictdata` endpoint from the home page. Fill in the student's demographic details and subject scores, hit the predict button, and the backend model will instantly infer and return the predicted math performance.

*Enjoy predicting student performance!* 🚀
