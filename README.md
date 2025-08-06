Project: XGBoost Visualization and Reporting Tools

Overview

This repository contains two Jupyter notebooks for working with XGBoost models:

Tree Renderer (ObtainTrees.ipynb)Loads a trained XGBoost model and its label encoder, computes the total number of decision trees, and generates Graphviz PDF visualizations for each tree with class labels in filenames.

Detailed Report Generator (ReportTrees.ipynb)Loads a CSV dump of XGBoost tree structures and feature data, reconstructs tree decision paths for a sample, outputs a detailed node-by-node report, computes class scores and softmax probabilities, and appends results to the output CSV.

Prerequisites

Python: Version 3.6 or higher (kernel for Jupyter notebooks)

Graphviz software (for rendering PDFs in ObtainTrees.ipynb)

Python packages:

xgboost, graphviz (for ObtainTrees.ipynb)

numpy, pandas (for ReportTrees.ipynb)

Installation

Install the required packages:

pip install xgboost graphviz numpy pandas

On Ubuntu/Debian, install Graphviz:

sudo apt-get install graphviz

Input Files

Place all required files in the same directory as the notebooks:

For ObtainTrees.ipynb:

xgboost_model.pkl — pickled XGBoost model

label_encoder.pkl — pickled LabelEncoder with class labels

For ReportTrees.ipynb:

xgboost_trees.csv — CSV dump of XGBoost trees (columns: Tree, Node, Feature, Split, Yes, No, Missing, Gain)

ns3_features_48Mbps.csv — CSV of feature values (columns correspond to feature names)

label_encoder.pkl — same as above

Usage

1. Tree Renderer

Open ObtainTrees.ipynb in Jupyter and run all cells.

This will:

Load xgboost_model.pkl and label_encoder.pkl.

Determine boosting rounds and class count.

Calculate total trees = rounds × classes.

Render each tree via Graphviz.

Save files tree_{index}_{class_label}.pdf.

2. Detailed Report Generator

Open ReportTrees.ipynb in Jupyter and run all cells.

This will:

Load xgboost_trees.csv, ns3_features_48Mbps.csv, and label_encoder.pkl.

Reconstruct tree structures in memory.

Select sample index 1 by default.

Traverse each tree, logging decisions and leaf gains.

Save detailed report to detailed_report_sample_1.csv.

Compute and append class scores and softmax probabilities.

Print confirmation of output file.

Output Examples

Tree Renderer:

tree_0_ClassA.pdf, tree_1_ClassB.pdf, …

Report Generator:

detailed_report_sample_1.csv (contains node data and appended summary)

Files in this Repository

ObtainTrees.ipynb      # XGBoost tree visualization notebook
ReportTrees.ipynb      # Detailed per-sample tree traversal and report notebook
xgboost_model.pkl      # Trained model (not included)
label_encoder.pkl      # Label encoder (not included)
xgboost_trees.csv     # Tree dump CSV (not included)
ns3_features_48Mbps.csv # Feature data CSV (not included)
README.md              # This file

