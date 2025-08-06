Detailed Tree and Sample Report Generator

Description

This script loads a CSV dump of XGBoost tree structures and a CSV of feature values, reconstructs the tree decision paths in memory, and generates a detailed per-node traversal report for a single sample. It also calculates class scores by summing leaf values, computes softmax probabilities, and appends the results to the same output CSV.

Prerequisites

Python 3.6 or higher

Python packages: numpy, pandas

Input Files

Place the following files in the same directory as the script before running:

xgboost_trees.csv (CSV dump of XGBoost trees with columns: Tree, Node, Feature, Split, Yes, No, Missing, Gain)

ns3_features_48Mbps.csv (CSV of feature values where each column is a feature name)

label_encoder.pkl (pickled LabelEncoder or equivalent containing class labels)

Installation

Install required Python packages by running:

pip install numpy pandas

Usage

Save the provided code into a file named generate_report.py

Ensure xgboost_trees.csv, ns3_features_48Mbps.csv, and label_encoder.pkl are in the same directory

Execute the script with the command:

python generate_report.py

The script will:

Load the tree dump and feature CSVs

Reconstruct tree structures in memory

Select a sample (index 1 by default)

Traverse each tree node-by-node, recording decisions and leaf gains

Build a detailed DataFrame and save it as detailed_report_sample_1.csv

Calculate class scores by summing leaf gains

Compute softmax probabilities across classes

Append the calculation summary and predicted class to the CSV

Example Output

detailed_report_sample_1.csv (contains traversal rows and appended report of class scores and probabilities)

Files

generate_report.py: Python script for report generation

xgboost_trees.csv: CSV dump of model trees

ns3_features_48Mbps.csv: CSV of sample features

label_encoder.pkl: Encoder mapping classes

License

This work is released into the public domain under the CC0 1.0 Universal license. You can copy, modify, and distribute it for any purpose without restriction.
