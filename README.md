# XGboost-Model-Analysis
This Code represent the analisys for XGBoost Models


XGBoost Model Tree Renderer

Description

This script loads a trained XGBoost model along with its associated label encoder, computes the total number of decision trees based on boosting rounds and class count, and iterates through each tree to generate Graphviz visualizations. Each generated tree is saved as a PDF file with the class label embedded in its filename.

Prerequisites

Python 3.6 or higher

Python packages: xgboost, graphviz

Graphviz software installed on your system for rendering PDF files

Input Files

Place the following files in the same directory as the script before running:

xgboost_model.pkl (pickled XGBoost model object)

label_encoder.pkl (pickled LabelEncoder or equivalent with class labels)

Installation

Install required Python packages by running:

pip install xgboost graphviz

On Ubuntu/Debian systems, install Graphviz using:

sudo apt-get install graphviz

Usage

Save the provided code into a file named render_trees.py

Ensure xgboost_model.pkl and label_encoder.pkl are in the same directory

Execute the script with the command:

python render_trees.py

Script steps:

Load the XGBoost model and label encoder

Determine the number of boosting rounds and classes

Calculate total trees as (boosting rounds × number of classes)

Render each tree using Graphviz

Save each visualization as tree_{index}_{class_label}.pdf

Example output printed to console:

Boosting rounds: 100Number of classes: 3Total trees to render: 300Rendering tree 0 for class 'ClassA'Rendering tree 1 for class 'ClassB'...All trees have been rendered with class names in their filenames.

Files

render_trees.py: Python script for rendering trees

xgboost_model.pkl: Trained XGBoost model file

label_encoder.pkl: Encoder mapping classes

License

This work is released into the public domain under the CC0 1.0 Universal license. You can copy, modify, and distribute it for any purpose without restriction.
