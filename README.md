# AdPredict — ML-Based CTR Prediction & Serving

## Project Overview  

**AdPredict** is an end-to-end project that predicts the probability of a user clicking an ad (CTR - Click Through Rate) using real-world style data.  
It includes model training, feature engineering, and a production-grade FastAPI backend with caching for fast, real-time predictions.

## Key Features  - ML pipeline: Logistic Regression (sklearn) trained on simulated click data
- FastAPI backend that serves predictions via a REST API
- In-memory LRU caching for repeated requests
- Load testing via simulated traffic (requests/sec)
- DSA used: heaps, dicts, LRU cache, sorting, feature hash maps

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

## Future Work
- Swap with real CTR dataset (e.g., Criteo, Avazu)
- Deploy with Docker + Gunicorn + NGINX
- Redis for distributed caching
