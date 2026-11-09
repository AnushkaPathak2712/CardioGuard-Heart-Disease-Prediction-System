# CardioGuard – Heart Disease Prediction System

An ML-powered web application that predicts the likelihood of heart disease using patient health parameters. Built with Python, Flask, and Logistic Regression.

**Live Demo:** https://cardioguard-heart-disease-prediction.onrender.com

**GitHub Repository:** https://github.com/AnushkaPathak2712/CardioGuard-Heart-Disease-Prediction-System

---

## 1. Project Overview

CardioGuard is a machine learning-based web application designed to predict the likelihood of heart disease based on medical parameters provided by users.

The system uses a Logistic Regression classification model trained on a structured heart disease dataset. Users can register, log in, enter health-related information, obtain prediction results, and view their prediction history.

The project combines machine learning with web development to demonstrate how predictive analytics can be integrated into a user-friendly application.

## 2. Key Features

- **Heart Disease Prediction:** Predicts the likelihood of heart disease using a trained machine learning model.
- **User Registration:** Allows new users to create accounts.
- **User Authentication:** Provides login and logout functionality.
- **Patient Input Form:** Collects relevant medical parameters for prediction.
- **Prediction Results:** Displays the model's prediction.
- **Prediction History:** Allows users to view previous predictions.
- **Informational Pages:** Provides information about heart disease.
- **Web-Based Interface:** Accessible through a browser without requiring local installation.

## 3. Technology Stack

| Component | Technology |
|---|---|
| Programming Language | Python |
| Machine Learning Algorithm | Logistic Regression |
| ML Framework | Scikit-learn |
| Data Processing | Pandas, NumPy |
| Backend Framework | Flask |
| Frontend | HTML, CSS, JavaScript |
| Database | SQLite |
| Model Serialization | Pickle |
| Development Platform | Google Colab, VS Code |
| Version Control | Git and GitHub |
| Deployment | Render |
| Production Server | Gunicorn |

## 4. Machine Learning Methodology

### Dataset Information

The project uses a structured heart disease dataset containing medical and clinical attributes.

| Attribute | Details |
|---|---|
| Dataset | Heart Disease Dataset |
| Source | Kaggle |
| Data Type | Structured / Tabular |
| Common Dataset Size | 303 records |
| Total Columns | 14 |
| Input Features | 13 |
| Target Variable | target |

*Note: The 303-record count refers to a commonly distributed version of the dataset. The exact record count should be confirmed from the dataset used in the notebook.*

### Input Features

The model uses 13 medical attributes:

| Feature | Description |
|---|---|
| age | Age of the patient |
| sex | Gender |
| cp | Chest pain type |
| trestbps | Resting blood pressure |
| chol | Serum cholesterol |
| fbs | Fasting blood sugar |
| restecg | Resting ECG results |
| thalach | Maximum heart rate achieved |
| exang | Exercise-induced angina |
| oldpeak | ST depression |
| slope | Slope of the ST segment |
| ca | Number of major vessels |
| thal | Thalassemia category |

### Target Variable

The target column represents the presence or absence of heart disease.

- `0` – No heart disease
- `1` – Heart disease

## 5. Data Preprocessing

The following data preparation steps were performed in the Google Colab notebook:

1. **Data Inspection:** Used `head()`, `tail()`, `info()` and `describe()` to understand the dataset.
2. **Missing Value Analysis:** Checked missing values using `isnull().sum()`.
3. **Feature Selection:** Separated independent variables (X) and the dependent target variable (Y).
4. **Train-Test Split:** Divided the dataset into 80% training data and 20% testing data.
5. **Stratified Sampling:** Used stratification to maintain the target class distribution in both subsets.
6. **Random State:** Used `random_state=2` for reproducibility.

The train-test split was implemented as follows:

```python
X = heart_data.drop(columns='target', axis=1)
Y = heart_data['target']

X_train, X_test, Y_train, Y_test = train_test_split(
    X,
    Y,
    test_size=0.2,
    stratify=Y,
    random_state=2
)
```

No explicit feature scaling, encoding, or class resampling was performed in the shared notebook implementation.

## 6. Machine Learning Algorithm

### Logistic Regression

CardioGuard uses Logistic Regression, a supervised machine learning classification algorithm.

It estimates the probability of a binary outcome using the logistic (sigmoid) function.

The model was implemented using Scikit-learn:

```python
from sklearn.linear_model import LogisticRegression

model = LogisticRegression()

model.fit(X_train, Y_train)
```

The trained model was serialized using Pickle and saved as:

`classifier.pkl`

The saved model is loaded by the Flask application to generate predictions from user-provided inputs.

### Model Evaluation

The notebook evaluates the model using training accuracy and testing accuracy.

```python
training_data_accuracy = accuracy_score(
    Y_train, X_train_prediction
)

test_data_accuracy = accuracy_score(
    Y_test, X_test_prediction
)
```

| Evaluation Metric | Result |
|---|---|
| Training Accuracy | To be updated |
| Testing Accuracy | To be updated |
| Precision | Not calculated in the shared notebook |
| Recall | Not calculated in the shared notebook |
| F1-Score | Not calculated in the shared notebook |

Numerical accuracy values should be added after checking the actual notebook output.

## 7. Web Application Architecture

The project integrates the trained machine learning model with a Flask web application.

**Application workflow:**

1. The user opens the CardioGuard web application.
2. The user registers or logs into their account.
3. The user enters the required medical parameters through the input form.
4. Flask receives the submitted information.
5. The application passes the input values to the trained Logistic Regression model.
6. The model generates a prediction.
7. Flask displays the prediction result.
8. Prediction information can be stored and viewed through prediction history.

### Architecture Flow

```text
        User
          |
          v
    Web Interface
   (HTML, CSS, JS)
          |
          v
     Flask Backend
          |
          v
   Input Processing
          |
          v
 Logistic Regression
    (classifier.pkl)
          |
          v
   Prediction Result
          |
          v
    SQLite Database
   (User & History Data)
```

## 8. Database

SQLite is used for database management.

The database supports application functionality such as:

- User account information.
- User authentication-related records.
- Prediction history.

The application uses Flask-SQLAlchemy for database integration.

## 9. Project Structure

```text
CardioGuard/
│
├── app.py
├── models.py
├── classifier.pkl
├── requirements.txt
├── Procfile
├── runtime.txt
├── .gitignore
├── README.md
│
└── templates/
    ├── index.html
    ├── homepg.html
    ├── login.html
    ├── register.html
    ├── history.html
    ├── forgot_password.html
    ├── reset_password.html
    ├── heart-disease-info.html
    └── heart-disease-nil.html
```

## 10. Installation and Local Setup

### Prerequisites

- Python 3.11
- Git
- Visual Studio Code (recommended)

### Step 1: Clone the repository

```bash
git clone https://github.com/AnushkaPathak2712/CardioGuard-Heart-Disease-Prediction-System.git
```

### Step 2: Navigate to the project directory

```bash
cd CardioGuard-Heart-Disease-Prediction-System
```

### Step 3: Create a virtual environment

```bash
python -m venv venv
```

### Step 4: Activate the virtual environment

For Windows:

```bash
venv\Scripts\activate
```

### Step 5: Install dependencies

```bash
pip install -r requirements.txt
```

### Step 6: Run the application

```bash
python app.py
```

Open the following URL in your browser:

```text
http://127.0.0.1:5000
```

## 11. Deployment

The application is deployed using Render.

**Deployment configuration:**

| Setting | Value |
|---|---|
| Hosting Platform | Render |
| Application Type | Python Web Service |
| Runtime | Python 3.11 |
| Build Command | `pip install -r requirements.txt` |
| Start Command | `gunicorn app:app` |
| Deployment Source | GitHub |

### Live Application

https://cardioguard-heart-disease-prediction.onrender.com

### GitHub Repository

https://github.com/AnushkaPathak2712/CardioGuard-Heart-Disease-Prediction-System

The application can be updated through GitHub by pushing new commits to the connected repository.

**Database deployment note:** The current application uses SQLite. Render's standard web-service filesystem is ephemeral, so database records may not persist across restarts or redeployments. PostgreSQL can be integrated for persistent database storage.

## 12. Future Enhancements

- Experiment with additional classification algorithms such as Random Forest, Decision Tree and Support Vector Machine.
- Improve model performance through hyperparameter tuning.
- Evaluate the model using precision, recall, F1-score and ROC-AUC.
- Apply cross-validation for more reliable performance evaluation.
- Use larger and more recent medical datasets.
- Enhance the user dashboard with graphical visualizations.
- Integrate PostgreSQL for persistent database storage.
- Generate downloadable prediction reports.
- Improve data validation and application security.

## 13. Disclaimer

CardioGuard is an educational machine learning project developed for academic purposes. Its predictions are not a substitute for professional medical advice, diagnosis, or treatment. The application should not be used to make independent medical decisions.

---

## Author

**Anushka Pathak**

Machine Learning | Python | Flask | Web Development

GitHub: https://github.com/AnushkaPathak2712

**Project: CardioGuard – Heart Disease Prediction System**