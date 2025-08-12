# Robustness Testing of Object Detection and Segmentation Models Under Camera Blemishes

**Author:** Your Name  
**Project:** Master_Thesis — Camera Blemish Impact on ADAS AI  
**Date:** 2025-08-12

---

## Overview
This project investigates the robustness of **object detection** and **segmentation** models (used in ADAS) when camera sensors exhibit manufacturing defects (referred to as *blemishes*). The main objective is to **derive measurable quality thresholds** for camera production by quantifying how blemishes affect downstream AI performance.

---

## Problem Statement
> How can we define camera quality acceptance gates for blemishes based on their measurable impact on downstream AI models used in ADAS?

This repository contains tools to:
- simulate blemishes on images,
- train/evaluate detection & segmentation models,
- analyze correlations between blemish characteristics and model performance,
- produce data-driven quality thresholds,
- deploy an end-to-end pipeline on Google Cloud Platform (GCP).

---

## Key Objectives
1. Simulate blemishes (dust, scratches, smudges, blur) using **OpenCV + Python**.  
2. Train & evaluate models: **YOLOv4**, **Fast R-CNN**, **FCN**.  
3. Quantify robustness & sensitivity of models to blemishes.  
4. Statistically correlate blemish parameters with performance drop (mAP, IoU, pixel accuracy).  
5. Define production quality gates for camera acceptance.  
6. Deploy pipeline on **Google Cloud Platform**.

---

## Quick Start

### Requirements
- Python 3.8+ (3.10 recommended)  
- GPU with CUDA for training (optional but recommended)  
- Install dependencies:
```bash
pip install -r requirements.txt


Blemish Simulation (example)
Model Training & Evaluation
Use train_yolo.py, train_frcnn.py, train_fcn.py to train models on clean and artificially blemished datasets.

evaluate.py computes:

Detection: mAP @ IoU thresholds (e.g., 0.5)

Segmentation: mean IoU, pixel accuracy

Use metrics.py to log performance vs. blemish parameters (size, opacity, location, density).

Statistical Analysis & Threshold Definition
Run experiments sweeping blemish parameters (size, opacity, density, location).

Aggregate results into a CSV with columns:
model, blemish_type, size, opacity, density, location, mAP, delta_mAP

Use regression / correlation (e.g., scikit-learn linear regression, decision trees, or logistic regression) to find relationships between blemish properties and performance drop.

Define quality gates such as:

"Reject if expected mAP drop > X% at production blemish distribution."

Or categorical: Accept / Conditional Accept / Reject thresholds.

# Reproducibility & Experiments

To ensure consistent and traceable research:

- Track all experiments (weights, configuration files, random seeds) in `results/experiments/`.
- Use deterministic seeds wherever possible for reproducibility.
- Save full configuration files alongside each checkpoint:
  - Model hyperparameters
  - Data augmentation list
  - Blemish simulation parameters

---

## Results & Expected Deliverables

This project will produce:

- **Plots** showing model performance vs. blemish severity.
- **Tables / CSV files** listing per-model quality thresholds.
- A reproducible blemish simulator (`src/blemish_sim.py`).
- GCP deployment scripts & a sample API endpoint.
- A final thesis document and the codebase to reproduce all experiments.

---

## Example Metrics to Report

- **Clean baseline** performance metrics:
  - mAP (Mean Average Precision)
  - IoU (Intersection over Union)
  - Pixel Accuracy (for segmentation)
- Performance under multiple blemish severities:
  - `delta_mAP = (mAP_clean - mAP_blemished) / mAP_clean * 100%`
- ROC-like curves showing:
  - Acceptance rate vs. false-pass rate for candidate quality gates

---

## How to Contribute

1. **Fork** the repository.
2. Create a feature branch:
   ```bash
   git checkout -b feat/your-feature
