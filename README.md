# SMS Scam Detection: Semi-Supervised Naive Bayes

This project implements a machine learning system designed to identify malicious SMS messages (scams) using a custom-built **Naive Bayes** classifier. It goes beyond basic supervised learning by incorporating a **semi-supervised self-training** loop to improve accuracy using unlabeled data.

## Features
* **Custom Naive Bayes:** Built from scratch (vocabulary building, frequency counting, and probability calculation) without relying on library-based classifiers.
* **Semi-Supervised Learning:** Implements an iterative "self-training" approach that identifies high-confidence predictions in unlabeled data to retrain and refine the model.
* **Performance Metrics:** Evaluates results using Accuracy, Precision, Recall, and F1-score.
* **Visualizations:** Includes confusion matrix heatmaps to track model improvement across different training iterations.

## Project Structure
.
├── scam_detection.ipynb   # Main Jupyter Notebook
├── datasets/              # Folder containing SMS CSV/TSV files
└── README.md              # Project documentation

## Installation & Requirements
To run this notebook, you will need Python 3 and the following libraries:
pip install numpy pandas matplotlib seaborn scikit-learn


## How it works
Supervised Phase: The model trains on a labeled dataset to learn the word distributions for "scam" vs "ham" (legitimate) messages.

Probability Thresholding: The program calculates an "r-score" (ratio of probabilities) to determine how confident the model is about a specific prediction.

Iterative Expansion: High-confidence unlabeled messages are automatically labeled by the model and added back into the training set to create a more robust classifier.

Evaluation: The final model is tested against a hidden test set to verify its ability to generalize to new, unseen scams.
