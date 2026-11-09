

An ML-powered web application that predicts the likelihood of heart disease based on user-provided medical parameters.

## About the Project

CardioGuard is a machine learning-based web application developed using Python and Flask. It allows users to enter relevant health parameters and receive a heart disease risk prediction.

The application also provides user authentication and prediction history management.

## Features

- Heart disease prediction using Machine Learning.
- User registration and login.
- Secure user authentication.
- Interactive web interface.
- Prediction history tracking.
- Database integration using SQLite.
- Informational pages about heart disease.

## Tech Stack

| Category | Technologies |
|---|---|
| Programming Language | Python |
| Backend | Flask |
| Machine Learning | Scikit-learn |
| Frontend | HTML, CSS, JavaScript |
| Database | SQLite |
| Model Storage | Pickle |
| Deployment | Render |
| Version Control | Git & GitHub |

## Project Structure

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
├── heart_disease_data.csv
│
└── templates/
    ├── index.html
    ├── homepg.html
    ├── login.html
    ├── register.html
    ├── history.html
    └── ...
```

## Installation and Setup

### 1. Clone the repository

```bash
git clone https://github.com/YOUR-USERNAME/CardioGuard.git
```

### 2. Navigate to the project directory

```bash
cd CardioGuard
```

### 3. Create a virtual environment

```bash
python -m venv venv
```

### 4. Activate the virtual environment

Windows:

```bash
venv\Scripts\activate
```

### 5. Install dependencies

```bash
pip install -r requirements.txt
```

### 6. Run the application

```bash
python app.py
```

Open your browser and visit:

```text
http://127.0.0.1:5000
```

## Deployment

The application is configured for deployment on **Render** using Gunicorn.

## Future Enhancements

- Improve prediction accuracy through model experimentation.
- Integrate additional machine learning algorithms.
- Enhance dashboard visualizations.
- Improve data security and user experience.

## Disclaimer

CardioGuard is an educational machine learning project. Its predictions are not a substitute for professional medical advice, diagnosis, or treatment.

---

**Developed as a Machine Learning and Web Development Project.**