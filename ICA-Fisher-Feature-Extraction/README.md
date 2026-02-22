# Advanced Feature Extraction: ICA & Fisher Segmentation Pipeline

## Overview
This project demonstrates advanced **Blind Source Separation (BSS)** and feature extraction using **Independent Component Analysis (ICA)** and **Fisher segmentation**. While demonstrated on complex visual arrays to isolate underlying structures, the core mathematical architecture is designed for decoupling mixed signals in quantitative finance and algorithmic modeling (e.g., isolating independent risk factors in noisy time series).

## Tech Stack
`R` | `Independent Component Analysis (ICA)` | `Fisher Segmentation` | `Blind Source Separation`

## Algorithm Highlights
* **Blind Source Separation (ICA):** Unlike PCA (which only decorrelates data), ICA maximizes non-Gaussianity to mathematically separate mixed, high-dimensional input arrays into strictly independent, non-overlapping signal components.
* **Fisher-Based Segmentation:** Applies Fisher's linear discriminant principles to dynamically segment and classify the extracted independent components, effectively filtering out background noise.
* **Signal Reconstruction:** Reconstructs the isolated components into distinct analytical layers, proving the ability to decompose complex data structures into actionable features.

## Project Structure
├── data/               # Original complex unstructured arrays (Ignored in Git)
├── notebooks/
│   └── 01_ica_fisher_extraction_pipeline.Rmd
├── reports/
│   └── project2_statistical_learning.html 
├── requirements.txt         # R dependencies (fastICA, MASS, tidyverse)
├── .gitignore
└── README.md

