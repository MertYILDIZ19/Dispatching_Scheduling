# Dispatching and Scheduling in Data Center Clusters
This repository contains the simulation engine, analytical models, and preprocessing scripts used in the study:

"*Dispatching Policies in Data Center Clusters: Insights from Google and Alibaba Workloads*"

The goal of this project is to provide a systematic and reproducible methodology to decompose the performance gaps between classical queueing theory and real-world production traces.

🚀 Overview
---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

We evaluate three core dispatching policies, all coupled with a First-Come-First-Served (FCFS) local scheduling policy:

Round Robin (RR)

Join-Idle-Queue (JIQ)

Least-Work-Left (LWL)

The codebase is organized into two primary experimental tracks:

**Synthetic Validation**: Comparison of analytical models against simulations using renewal-based workloads. These experiments use Poisson arrivals and Weibull-distributed service times to validate the theoretical foundations of the policies.

**Trace-Driven Analysis**: Detailed simulation of production workloads from Google and Alibaba. This includes our Feature-Attribution Framework (shuffling, trimming, and Poisson replacement) used to isolate specific performance drivers.

📊 Data Sources
---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

Due to size and licensing restrictions, raw traces are not hosted here. Please download them from the official repositories:

Google ClusterData v3 (2019): [🔗 here](https://github.com/MertYILDIZ19/Google_cluster_usage_traces_v3_all_cells)

Alibaba Cluster Trace v2018: [🔗 here](https://github.com/MertYILDIZ19/Alibaba_cluster_usage_traces_2018)

Setup: Once downloaded, update the data path variables within the Jupyter Notebooks to point to your local files.


📂 Repository Structure & Usage
---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

🧪 **Synthetic Validation**
Data Requirement: No external data is required.

File: Weibull_Workload_Model_Validation.ipynb

Details: Arrivals and service times are generated synthetically within the notebook.

Customization: You can modify the Coefficient of Variation (CoV) within the parameters cell to test different variability scenarios.


📉 **Real Workload Analysis**

*Discrepancy Analysis*: Focuses on the gap between analytical models (driven by the first two moments of IAT/Service times) and the raw data-driven simulation.

- Check: Model_Simulations_Original.ipynb

*Model Matching*: Demonstrates how analytical models align with the simulation once the data is fully shuffled and extreme outliers are removed (as detailed in the paper).

- Check: Model_Simulations_Matching.ipynb

*Task-Level Simulations*: To reproduce task-level results, replace the input with task-level datasets. Note that Mean Response Time is always calculated at the Job level.


🔬 Methodology Reference
---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

The systematic decomposition methodology is the core of this research. It involves the following sequential steps to isolate performance impacts:

- Shuffling Inter-Arrival Times (IAT).

- Replacing arrivals with a Poisson process.

- Shuffling service times.

- Trimming the top 0.1% of "elephant" jobs/tasks.

🎓 Citation
---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

If you use this code or methodology in your research, please cite our work:

Kod snippet'i
@article{yildiz2025dispatching,
  title={Dispatching Policies in Data Center Clusters: Insights from Google and Alibaba Workloads},
  author={Yildiz, Mert and Rolich, Alexey and Baiocchi, Andrea},
  journal={Performance Evaluation},
  year={2026}
}
