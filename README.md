# AdPredict — ML-Based CTR Prediction & Serving

## Project Overview  
AdPredict is an end-to-end system that predicts click-through rates (CTR) for ad impressions, and serves predictions in real time.  
It includes model training, feature engineering, and a scalable backend API which handles high throughput with caching and load balancing.

## Key Features  
- Feature engineering pipeline in `utils/features.py`  
- Model training (e.g. logistic regression, XGBoost) in `model/train.py`  
- REST API prediction server using FastAPI in `service/server.py`  
- Request simulation tool in `scripts/simulate_requests.py`  
- Caching and request-level optimization (LRU cache, sharding, etc.)

## How to Run  
1. `pip install -r requirements.txt`  
2. Prepare data under `data/sample_dataset.csv`  
3. Train model: `python model/train.py`  
4. Run service: `uvicorn service.server:app --host 0.0.0.0 --port 8000`  
5. Simulate load: `python scripts/simulate_requests.py`

## Tech Stack  
- Python, FastAPI  
- Scikit-learn / XGBoost  
- Redis (for caching)  
- Docker + Kubernetes (optional, for deployment)  
- DSA: LRU cache, priority queues, sharding logic

## What to Improve  
- Add logging, monitoring, rate limiting  
- Scale horizontally with autoscaling  
- Integrate feedback loop to update model in production



# 🚀 AdPredict — CTR Prediction with Scalable Real-Time ML Backend

**AdPredict** is an end-to-end project that predicts the probability of a user clicking an ad (CTR - Click Through Rate) using real-world style data.  
It includes model training, feature engineering, and a production-grade FastAPI backend with caching for fast, real-time predictions.

---

## 🔧 Features

- ML pipeline: Logistic Regression (sklearn) trained on simulated click data
- FastAPI backend that serves predictions via a REST API
- In-memory LRU caching for repeated requests
- Load testing via simulated traffic (requests/sec)
- DSA used: heaps, dicts, LRU cache, sorting, feature hash maps

---

## 🚀 How to Run

```bash
git clone https://github.com/yourusername/AdPredict.git
cd AdPredict
pip install -r requirements.txt

# Step 1: Train model
python model/train_model.py

# Step 2: Start prediction API server
uvicorn service.server:app --host 0.0.0.0 --port 8000

# Step 3: Simulate ad requests
python scripts/simulate_requests.py

