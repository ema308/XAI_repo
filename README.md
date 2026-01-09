# Subgroup Discovery in Textual Data Using Statistical Metadata and BERT Uncertainty Analysis
This repository contains the code and experiments for a study on identifying problematic subgroups within textual datasets (IMDB Dataset of 50K Movie Reviews and Twitter US Airline Sentiment) using subgroup discovery techniques originally designed for tabular data. The project bridges Natural Language Processing (NLP) and exploratory data mining by converting unstructured text into structured metadata and analyzing model uncertainty across different text subgroups.
## Overview
For each dataset, three main steps were applied: <br>
**1. Text-to-Table Transformation**
    Each text sample is processed to extract statistical features, such as: <br>
    - Text length <br>
    - Sentence and word counts <br>
    - Token distribution patterns <br>

**2. Uncertainty Detection with BERT**
    A BERT-based sequence classification model is trained on the target dataset.
    Prediction uncertainty is defined using a probability threshold p*, where a prediction is marked uncertain if model confidence < p*. The value of p* is chosen so that at least 10% of the test set is labeled as uncertain, ensuring a sufficiently large subset for subgroup analysis.

**3. Subgroup Discovery with DivExplorer**
   The resulting tabular dataset (metadata + uncertainty labels) is analyzed using the DivExplorer algorithm.

## Code and usage
The folder `Code` contains two Jupyter notebooks that provide detailed code for the steps described above. Each notebook corresponds to one of the employed datasets (IMDB Dataset of 50K Movie Reviews and Twitter US Airline Sentiment). The .csv files for the datasets are located in the `Data` folder. 
## Results
Across experiments, the analysis revealed: <br>

- Lower divergence values in longer texts, suggesting that the BERT classifier is more confident when processing longer or more complex textual inputs.

- The subgroup discovery process successfully highlighted text-based patterns associated with uncertainty.

- The methodology enables a systematic approach to identifying dataset subgroups that may cause model bias or instability.

## Acknowledgements
This project is part of the final exam of the "Explainable and Trusthworthy AI" course at Politecnico di Torino
