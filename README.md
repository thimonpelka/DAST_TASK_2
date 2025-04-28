# Predicting Rocket League Skillshots Using Machine Learning

## Project Overview

This project applies machine learning techniques to predict the type of **Rocket League skillshot** executed just before a goal is scored.
Using data from the last 30 frames before each goal, a variety of player and ball features (position, speed, inputs, etc.) were collected and analyzed.
The goal is to automatically classify the executed skillshot into one of seven categories.

Originally developed as an adapted exercise from a machine learning course, the project was expanded to apply **FAIR data principles**:
- Data is stored in a university-internal DBRepo instance with a DOI.
- Results and models are uploaded to the TU Wien Research Data platform (TUWRD).

## Repository Structure

| File | Description |
|:-----|:------------|
| `notebook.ipynb` | Main Python Notebook containing all code for data preprocessing, modeling, evaluation, and exporting results. |
| `requirements.txt` | List of Python package dependencies for running the notebook. |
| `dataDictionary.md` | Full data dictionary describing each column of the dataset, including units, labels, and notes on missing data. |
| `.env` | Environment variable file containing placeholders for personal credentials (required to access DBRepo and TUWRD). |
| `models/` | Folder containing trained model `.pkl` files. |
| `results/` | Folder containing prediction outputs, confusion matrices, and performance evaluations. |

## Quick Start

### 1. Set up your environment

- Python version **>= 3.11** is recommended.
- Install the required packages:

```bash
pip install -r requirements.txt
```
