
# Awesome Bioengineering Datasets for Fermentation Research

A curated collection and guide for publicly available, reliable, and validated datasets for fermentation process modeling, control, and advanced data science applications.

This repository focuses on bridging the gap between **Bioengineering** (bioprocess dynamics) and **Electrical Engineering / Computer Science** (advanced control, machine learning, and soft-sensing).

---

## 🚀 Featured Benchmark: IndPenSim (Industrial Penicillin Simulation)

The primary dataset recommended for research in this repository is sourced from the **Industrial Penicillin Simulation Platform**:
🔗 **Official Source:** [http://industrialpenicillinsimulation.com](http://industrialpenicillinsimulation.com)

### 📌 Dataset Profile: IndPenSim

IndPenSim is a world-class, industrially validated benchmark dataset that replicates a **100,000-L industrial-scale fed-batch penicillin fermentation process**. It perfectly captures the complex, non-linear, and multirate nature of bioprocesses.

| Feature | Specification / Details | Engineering Significance |
| :--- | :--- | :--- |
| **Process Type** | Fed-batch (100,000 Liters) | Captures long-term dynamic time-series |
| **Variables** | 30+ Process Parameters (Online + Offline) | High-dimensional data for machine learning |
| **Batches** | Standard 100 batches (Training) + 300 batches | Large-scale data for robust model validation |
| **Validation** | Verified by industrial experts & peer-reviewed | Highly reliable, containing realistic noise/faults |

---

## 📊 Detailed Variable Breakdown (For EE & AI Researchers)

To help researchers from Electrical Engineering / Data Science quickly understand the data structure, the variables from the IndPenSim platform are classified into two major categories:

### 1. Critical Process Parameters (CPPs) - Online Continuous Sensors
These variables are sampled at a **high frequency (e.g., every 12 minutes)** and are readily available for real-time feedback control:
* **Thermal & Agitation:** Temperature, Cooling water flow rate, Agitation power, Vessel weight.
* **Chemical Environment:** pH, Dissolved Oxygen (DO), Aeration rate, Substrate feed rate.
* **Off-gas Analysis:** Carbon dioxide percent ($CO_2$), Oxygen percent ($O_2$) in off-gas.

### 2. Critical Quality Attributes (CQAs) - Offline Laboratory Measurements
These variables are sampled at a **low frequency (e.g., every 2 to 4 hours)** via manual extraction and HPLC analysis:
* **Biomass Concentration ($X$)** - Cell growth.
* **Penicillin Concentration ($P$)** - Product yield.
* **Substrate Concentration ($S$)** - Glucose/Feed levels.

---

## 🛠️ Cross-Disciplinary Research Use Cases

If you are leveraging the IndPenSim platform data, here are the most impactful research directions intersecting Bioengineering and EE:

### 💡 1. Soft-Sensor Development (Virtual Sensors)
* **The Challenge:** Offline CQAs (like Biomass and Penicillin yield) cannot be measured in real-time due to lab delays.
* **EE Solution:** Use recurrent neural networks (LSTM, GRU) or Transformers to predict offline concentrations in real-time using fast online sensor data (pH, DO, Temp).

### 💡 2. Fault Detection and Isolation (FDI)
* **The Challenge:** Biological systems are sensitive; sensor drift or actuator failures (e.g., feed pump blockage) can ruin a 200-hour batch.
* **EE Solution:** Implement PCA, PLS, or Deep Autoencoders for multi-way statistical process monitoring (MSPM) to detect anomalies early.

### 💡 3. Reinforcement Learning & Model Predictive Control (MPC)
* **The Challenge:** Fermentation is highly non-linear, making traditional PID control sub-optimal for feeding strategies.
* **EE Solution:** Design Non-linear MPC or Reinforcement Learning (RL) agents to optimize the feeding rate to maximize yield while preventing overflow metabolism.

---

## 🤝 Citation & Academic Respect

When using this dataset or code, please respect the original creators by citing their landmark papers and acknowledging the platform:
1. **Platform Link:** [Industrial Penicillin Simulation Platform](http://industrialpenicillinsimulation.com)
2. **Key Literature:** Goldrick, S., et al. (2015). *The development of an industrial-scale penicillin simulation.* Journal of Biotechnology.

