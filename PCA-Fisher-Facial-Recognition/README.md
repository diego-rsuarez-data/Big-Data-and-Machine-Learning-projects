# Biometric Facial Recognition: PCA & FDA Pipeline

## Overview
A lightweight, from-scratch facial authentication system using Statistical Machine Learning. The model extracts core facial features, maximizes separability between individuals, and uses optimized distance thresholds to authenticate registered users and reject intruders.

## Tech Stack
`R` | `PCA (Eigenfaces)` | `FDA (Fisherfaces)` | `KNN` | `Computer Vision`

## Project Structure
├── data/
│   ├── Training/            # Database of known faces (Registered identities)
│   └── Testing2/            # External faces to test intruder detection
├── notebooks/
│   └── 01_facial_recognition_pipeline.Rmd
├── requirements.txt         # R dependencies (tidyverse, caret, Matrix, jpeg)
├── install_packages.R       # Environment setup script
├── .gitignore               # Ignores image datasets and R temporary files
└── README.md

## Algorithm Highlights
* **PCA (Eigenfaces):** Reduces the high dimensionality of flattened image matrices, preserving maximum variance while filtering out background noise.
* **FDA (Fisherfaces):** Applied over the PCA space to maximize between-class scatter and minimize within-class scatter, tightly clustering images of the same identity.
* **KNN & Statistical Thresholding:** Uses optimized spatial metrics (Cosine/Euclidean) to classify identities and applies an intra-class distance boundary to accurately flag non-registered users.
