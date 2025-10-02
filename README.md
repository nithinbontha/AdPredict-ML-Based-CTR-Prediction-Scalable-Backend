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
