# Gym_QoE

This repository contains the code and experiments for the paper:

**"Reinforcement Learning-based Orchestration of XR applications in Distributed 6G Cloud Infrastructures"**, published at **CNSM 2025**. 
Link to the paper : https://biblio.ugent.be/publication/01K94V3M7M429P9N5JGS9DVHEX

---

## 🚀 Getting Started

### 📦 Prerequisites

Ensure you have the required Python packages installed:

```bash
pip install -r requirements.txt
```

---

## 🧠 Running the RL Agents

You can train and test reinforcement learning agents in the Gym-QoE environment using the `run_csv.py` script. This script supports multiple RL algorithms and configurations defined in a CSV file.

### 🔧 Example: Training a Model

Run the following command to train a model using the configuration from `execution_config.csv`:

```bash
python run_csv.py \
  --alg mask_ppo \
  --env_name nne \
  --num_nodes 4 \
  --reward multi \
  --training \
  --steps 50000 \
  --total_steps 200000
```

### 📋 What This Script Does

- Loads training/testing configurations from `execution_config.csv`
- Trains and (optionally) tests models for each configuration
- Saves trained models to `./models/`
- Logs training metrics to `./logs/` and `./results/`
- Records performance data in:
  - `./run_metrics/*.csv` (training)
  - `./run_metrics_test/*.csv` (testing)

---

## 📂 Output Structure

- **Logs:** `./logs/[run_name]/`
- **Trained Models:** `./models/[run_name].zip`
- **Metrics CSVs:**
  - Training: `./run_metrics/*.csv`
  - Testing: `./run_metrics_test/*.csv`
- **TensorBoard Logs:** `./results/[env]/[reward]/`

### 📈 Visualize with TensorBoard

To visualize training performance:

```bash
tensorboard --logdir ./results
```

---

## 📊 Performance Analysis

Use the provided `Analysis.ipynb` notebook to explore and compare algorithm performance across experiments.

---

## 📄 License

This code is made available for academic and research purposes only. Please cite the paper if you use this work.
