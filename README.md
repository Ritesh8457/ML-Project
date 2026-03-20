# Student Performance Prediction 🎓📊

This is an End-to-End Machine Learning project focused on predicting student math performance based on their demographic information, parental level of education, lunch plan, and test preparation score. It includes a complete data pipeline (ingestion, transformation, modeling), robust logging & exception handling, and a web interface for predictions.

## 🚀 Web Server Code
The application exposes a web interface created with **Flask**. 
You can find the core web server logic in these files:
- 🔗 [`app.py`](./app.py): The main Flask server application which defines the routing for the home page (`/`) and the prediction endpoint (`/predictdata`).
- 🔗 [`application.py`](./application.py): Specifically configured for cloud deployments such as AWS Elastic Beanstalk (which looks for `application.py` by default).

## 🛠️ Project Architecture 
The project follows a standard and modular machine learning pipeline structure:

```
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
├── nootebook/                     # 📓 Jupyter notebooks for EDA and Model training
├── requirements.txt               # 📜 Python dependencies
└── setup.py                       # 🛠️ Script to make `src` a local package
```

## ⚙️ Tech Stack Used
* **Backend Framework:** Flask
* **Machine Learning:** Scikit-Learn, CatBoost, XGBoost
* **Data Processing:** Pandas, NumPy
* **Visualization (in notebooks):** Seaborn, Matplotlib
* **Serialization:** dill

## 📥 How to Run Locally

1. **Clone the repository** (if you're pulling from Git):
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

3. **Install exactly the required dependencies:**
   ```bash
   pip install -r requirements.txt
   ```

4. **Run the Flask application:**
   ```bash
   python app.py
   ```
   **OR**
   ```bash
   python application.py
   ```

5. **Open your browser** and navigate to:
   [http://127.0.0.1:5000/](http://127.0.0.1:5000/)

## 📝 Usage
Once the application is running, navigate to the `/predictdata` endpoint from the home page. Fill in the student's demographic details and subject scores, hit the predict button, and the backend model will instantly infer and return the predicted math performance.

*Enjoy predicting student performance!* 🚀
