# 🍷 Wine Quality Prediction – Mini MLOps Project

![Python](https://img.shields.io/badge/python-3.11%20%7C%203.13-blue)
![Flask](https://img.shields.io/badge/flask-1.1.2-green)
![Docker](https://img.shields.io/badge/docker-enabled-blue)
![CI](https://img.shields.io/badge/ci-github_actions-brightgreen)
![MLflow](https://img.shields.io/badge/mlflow-enabled-lightgrey)
![DVC](https://img.shields.io/badge/dvc-data_versioning-orange)
![AWS](https://img.shields.io/badge/aws-cloud-orange)

This repository showcases a clean, end-to-end MLOps workflow using a simple wine quality prediction model.  
It is designed to be easy to understand for learners while also demonstrating practical MLOps skills that recruiters and hiring managers look for.

---

## 🎯 Project Goal

Build, train, package, and deploy a machine-learning model using modern MLOps practices, including:

- Reproducible training  
- Artifact generation  
- CLI inference  
- API deployment  
- Containerization  
- CI-driven automation

This project is intentionally small, focused, and production-oriented.
<img width="1264" height="958" alt="image" src="https://github.com/user-attachments/assets/942a1447-542c-4a2e-aad1-1914934d389d" />

---

## 🔁 MLOps Flow (High Level)

1. **Train the model**  
   `train.py` trains a small ML model and stores:  
   - `artifacts/model.pkl`  
   - `artifacts/metrics.json`  

2. **Run predictions locally**  
   `run_model.py` allows quick CLI inference.

3. **Serve the model**  
   A Flask API exposes a `/predict` endpoint.

4. **Containerize the application**  
   Docker builds a portable, deployable image.

5. **CI pipeline**  
   Automatically trains the model and uploads artifacts.

---

## 🚀 Quick Start (Local)

### 1️⃣ Create & activate a virtual environment

```bash
python -m venv .venv
source .venv/bin/activate
pip install --upgrade pip setuptools wheel
pip install -r requirements.txt
python train.py
```
artifacts/
├── model.pkl
└── metrics.json

4️⃣ Run a prediction from the CLI
``` python run_model.py --input "[5.1, 3.5, 1.4, 0.2]"```

4️⃣ Run a prediction from the CLI
```python run_model.py --input "[5.1, 3.5, 1.4, 0.2]" ```

5️⃣ Start the API
```python src/app.py```


Test the endpoint:
```
curl -X POST "http://127.0.0.1:5000/predict" \
-H "Content-Type: application/json" \
-d '{"features":[5.1,3.5,1.4,0.2]}'
```
🐳 Build and run the Docker image:
```
docker build -t mlops-wp-model.
docker run -p 5000:5000 mlops-wp-model
```
🛠️ Tools & Technologies Used
```
Python
scikit-learn
pandas
Flask
MLflow – experiment tracking
DVC – data & artifact versioning
PostgreSQL (via AWS RDS) – metadata / storage
AWS – cloud infrastructure
Docker – containerization
GitHub Actions – CI pipeline
Virtual Environments (venv)
```
---
