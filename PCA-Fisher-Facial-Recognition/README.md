# Biometric Facial Recognition: PCA & FDA Pipeline

## Overview
A lightweight, from-scratch facial authentication system using Statistical Machine Learning. The model extracts core facial features, maximizes separability between individuals, and uses optimized distance thresholds to authenticate registered users and reject intruders.

## Tech Stack
`R` | `PCA (Eigenfaces)` | `FDA (Fisherfaces)` | `KNN` | `Computer Vision`

## Project Structure

- `data/` — Facial images organized in `Training/` and `Testing2/` (external/intruders).
- `notebook/` — RMarkdown notebook (`facial_recognition_pipeline.Rmd`) implementing the mathematical core.
- `report/` — HTML report with performance metrics and distance distribution plots.
- `requirements.txt` — List of R dependencies (caret, tidyverse, Matrix, jpeg).
- `README.md` — Project description and instructions.

## Algorithm Highlights
* **PCA (Eigenfaces):** Reduces the high dimensionality of flattened image matrices, preserving maximum variance while filtering out background noise.
* **FDA (Fisherfaces):** Applied over the PCA space to maximize between-class scatter and minimize within-class scatter, tightly clustering images of the same identity.
* **KNN & Statistical Thresholding:** Uses optimized spatial metrics (Cosine/Euclidean) to classify identities and applies an intra-class distance boundary to accurately flag non-registered users.
