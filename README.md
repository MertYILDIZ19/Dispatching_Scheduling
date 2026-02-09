## Dispatching and Scheduling in Data Center Clusters

This repository contains the simulation engine, analytical models, and preprocessing scripts used in the study: "Dispatching Policies in Data Center Clusters: Insights from Google and Alibaba Workloads".

The goal of this project is to provide a systematic and reproducible methodology to decompose the performance gaps between classical queueing theory and real-world production traces.

🚀 Overview
We evaluate three core dispatching policies:

Round Robin (RR)

Join-Idle-Queue (JIQ)

Least-Work-Left (LWL)

The code is organized into two main experimental tracks:

Synthetic Validation: Comparison of analytical models against simulations using renewal-based workloads (Poisson arrivals and Weibull-distributed service times).

Trace-Driven Analysis: Simulation of production workloads from Google and Alibaba, including the feature-attribution framework (shuffling, trimming, and Poisson replacement) to isolate performance drivers.

📊 Data Sources
Due to size and licensing, the raw traces are not hosted in this repository. You can request access and download them from the official sources below:

Google ClusterData v3 (2019): Google Cluster Data GitHub

Alibaba Cluster Trace v2018: Alibaba Cloud Architecture GitHub

Once downloaded, place the traces in the /data directory following the instructions in the preprocessing/ folder.
