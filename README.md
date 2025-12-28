# 🍽️ Restaurant Supply Optimizer

### Autonomous Inventory Management via `Rainbow DQN`

**Status:** Production Tested — **99.9% Service Level**


---

## 🧠 Executive Summary


The **Restaurant Supply Optimizer** solves the classic *inventory balancing act* for high-volume restaurants:  
**eliminating stockouts while minimizing perishable waste.**


By combining a **30-day Neural Demand Forecaster** with a **Rainbow DQN reinforcement learning agent**, the system autonomously makes procurement decisions under:


- Volatile demand  
- Perishable inventory constraints  
- Fixed supplier delivery windows  


The result is a **fully automated purchasing engine** that consistently outperforms traditional heuristic-based ordering strategies.


---

## 🛠️ Tech Stack


- **Language:** Python  
- **Reinforcement Learning:** PyTorch (`Rainbow DQN`)  
- **Infrastructure:** GCP Cloud Run  
- **Data Warehouse:** BigQuery  
- **Containerization:** Docker  


---

## 📈 Key Performance Metrics (Production Testing)


Evaluated against **real-world restaurant data** under realistic operational constraints:


| Metric | Result |
|------|------|
| **Product Availability** | **99.9%** (near-elimination of stockouts) |
| **Average Waste** | **3.5%** (industry-leading for perishables) |
| **Efficiency Gain** | ~**15%** waste reduction vs Min–Max heuristics |


> Achieved even under **no-restock windows** and variable supplier lead times.


---

## ⚙️ System Architecture


### 1️⃣ Forecasting Engine (Demand Lookahead)


Before the RL agent acts, a neural forecasting model generates a **30-day demand horizon** using:


- Historical sales  
- Seasonality effects  
- Learned embeddings  


This foresight enables the agent to plan across supplier blackout periods and avoid both overstocking and shortages.


---

### 2️⃣ Reinforcement Learning Agent — `Rainbow DQN`


The core decision-maker is a **Rainbow DQN** agent designed for improved stability and sample efficiency.


**Environment:** Custom Gymnasium simulation


**State Space:**


- Current inventory levels  
- Forecasted 30-day demand  
- Ingredient shelf-life / decay curves  
- Supplier delivery schedules  


**Action Space:**


- Discrete purchase quantities per ingredient  


**Reward Function:**


A multi-objective reward penalizing:


- **Waste** (expired inventory)  
- **Shortfall** (lost sales / stockouts)  


Reward weights are tuned to **prioritize near-100% service levels**.


---

### 3️⃣ Deployment & Scalability


- **Microservices:** Containerized services deployed on **GCP Cloud Run**  
- **Data Pipeline:** Automated daily ETL from **BigQuery** to refresh agent state  
- **Interface:** Generates clear, item-by-item purchase recommendations for restaurant operators  


---

## 🧪 Training & Simulation


The agent is trained in a **high-fidelity simulation environment** modeling real operational complexity:


- 🧊 **Ingredient Decay:** Shelf-life tracking across categories  
- 🚚 **Supplier Constraints:** Fixed shipping days and lead-time volatility  
- 📦 **No-Restock Windows:** Forced planning under supply gaps  


This enables **safe and scalable training** prior to live deployment.


---

## 🔒 Privacy & Code Access


All proprietary code and restaurant data are **internal to Wizdorant**.


This repository provides a **high-level technical overview** of:


- System architecture  
- Modeling approach  
- Production performance benchmarks  


---

## 📌 Use Cases


- High-volume restaurants  
- Multi-location food operators  
- Perishable-heavy menus  
- Automated procurement & inventory optimization
