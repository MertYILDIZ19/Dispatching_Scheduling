# Dispatching and Scheduling in Data Center Clusters
This repository contains the simulation engine, analytical models, and preprocessing scripts used in the study: "Dispatching Policies in Data Center Clusters: Insights from Google and Alibaba Workloads".

The goal of this project is to provide a systematic and reproducible methodology to decompose the performance gaps between classical queueing theory and real-world production traces.

---------------------------------------------------------------------------------------------------------------------------------------------------------

🚀 Overview
We evaluate three core dispatching policies, all coupled with a First-Come-First-Served (FCFS) local scheduling policy:

Round Robin (RR)

Join-Idle-Queue (JIQ)

Least-Work-Left (LWL)

The codebase is organized into two experimental tracks:

1. Synthetic Validation
Comparison of analytical models against simulations using renewal-based workloads. These experiments use Poisson arrivals and Weibull-distributed service times to validate the theoretical foundations of the policies.

2. Trace-Driven Analysis
Detailed simulation of production workloads from Google and Alibaba. This includes our Feature-Attribution Framework (shuffling, trimming, and Poisson replacement) used to isolate specific performance drivers like temporal dependence and service time outliers.

📊 Data Sources
Due to size and licensing restrictions, raw traces are not hosted here. Please download them from the official repositories:

Google ClusterData v3 (2019): Google GitHub Repository

Alibaba Cluster Trace v2018: Alibaba GitHub Repository

Setup: Once downloaded, update the data path variables in the provided Jupyter Notebooks to point to your local files.

📂 Repository Structure & Usage
🧪 Synthetic Validation
Data Requirement: No external data is required.

File: Synthetic_Validation.ipynb

Details: Arrivals and service times are generated directly in the notebook.

Customization: You can easily modify the Coefficient of Variation (CoV) within the parameters cell to test different variability scenarios.

📉 Real Workload Analysis
Notebook 1 (Discrepancy Analysis): Focuses on the gap between analytical models (driven by the first two moments of IAT/Service times) and the raw data-driven simulation.

Notebook 2 (Model Matching): Demonstrates how analytical models align with the simulation once the data is fully shuffled and extreme outliers are removed (as detailed in the paper).

Task-Level Simulations: To reproduce task-level results, replace the input with task-level datasets. Note that Mean Response Time is always calculated at the Job level.

🔬 Methodology Reference
The systematic decomposition methodology is the core of this research. It involves:

Shuffling Inter-Arrival Times (IAT).

Replacing arrivals with a Poisson process.

Shuffling service times.

Trimming the top 0.1% of "elephant" jobs/tasks.
