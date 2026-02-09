# Dispatching and Scheduling in Data Center Clusters

This repository contains the **simulation engine**, **analytical models**, and **preprocessing scripts** used in the study: 
> *"Dispatching Policies in Data Center Clusters: Insights from Google and Alibaba Workloads"*

The goal of this project is to provide a **systematic and reproducible methodology** to decompose the performance gaps between *classical queueing theory* and *real-world production traces*.

---

## 🚀 Overview
We evaluate three core dispatching policies, all coupled with a **First-Come-First-Served (FCFS)** local scheduling policy:

* **Round Robin (RR)**
* **Join-Idle-Queue (JIQ)**
* **Least-Work-Left (LWL)**

The codebase is organized into two primary experimental tracks:

1. **Synthetic Validation:** Comparison of analytical models against simulations using renewal-based workloads (*Poisson arrivals* and *Weibull-distributed service times*).
2. **Trace-Driven Analysis:** Detailed simulation of production workloads from Google and Alibaba, including our *Feature-Attribution Framework* to isolate specific performance drivers.

---

## 📊 Data Sources
Due to size and licensing, raw traces are not hosted here. Please download them from:
* **Google ClusterData v3 (2019):** [Google GitHub](https://github.com/MertYILDIZ19/Google_cluster_usage_traces_v3_all_cells)
* **Alibaba Cluster Trace v2018:** [Alibaba GitHub](https://github.com/MertYILDIZ19/Alibaba_cluster_usage_traces_2018)

**Setup:** Once downloaded, update the data path variables in the notebooks to point to your local files.

---

## 📂 Repository Structure & Usage

### 🧪 Synthetic Validation
* **File:** `Weibull_Workload_Model_Validation.ipynb`
* *Details:* No external data required; arrivals/service times are generated in-notebook.
* *Customization:* Modify the **Coefficient of Variation (CoV)** in the parameters cell to test variability.

### 📉 Real Workload Analysis
* **Discrepancy Analysis:** Examines the gap between raw trace simulations and analytical models. 
  * *Notebook:* `Model_Simulations_Original.ipynb`
* **Model Matching:** Shows how theory aligns with data after shuffling and outlier removal.
  * *Notebook:* `Model_Simulations_Matching.ipynb`
* **Task-Level Simulations:** Replace input with task-level datasets to reproduce task-granularity insights.

---

## 🎓 Citation
If you use this code or methodology, please cite:

```bibtex
@article{yildiz2025dispatching,
  title={Dispatching Policies in Data Center Clusters: Insights from Google and Alibaba Workloads},
  author={Yildiz, Mert and Rolich, Alexey and Baiocchi, Andrea},
  journal={Performance Evaluation},
  year={2026}
}
