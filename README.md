# COMP 541 Data Mining Final Project

## Instacart Produce Department Analysis

> COMP 541 Data Mining final project analyzing Instacart Produce purchases with statistical analysis, FP-Growth association rule mining, cross-department pattern mining, and K-means clustering.

![Python](https://img.shields.io/badge/Language-Python-blue)
![Jupyter](https://img.shields.io/badge/Notebook-Jupyter-orange)
![Data Mining](https://img.shields.io/badge/Topic-Data%20Mining-purple)
![FP-Growth](https://img.shields.io/badge/Method-FP--Growth-green)
![Clustering](https://img.shields.io/badge/Method-K--Means-red)

---

## About

This repository contains my **COMP 541: Data Mining** final project from Spring 2026.

The project analyzes the **Produce** department from the Instacart training-order dataset. The goal was to move beyond simple grocery co-purchase observations and identify more meaningful patterns using statistical analysis, frequent pattern mining, cross-department association rules, and clustering.

The analysis was completed in Python using a Jupyter Notebook.

---

## Project Objective

The project requirements included:

- Selecting one Instacart department for analysis
- Using the full training-order dataset without sampling
- Completing at least three statistical analyses
- Completing at least three pattern-mining analyses
- Applying Apriori or FP-Growth
- Reporting support counts and confidence values
- Explaining threshold choices
- Adding an optional extra-credit insight

This project selected the **Produce** department and used FP-Growth for product-level, aisle-level, and cross-department association mining.

---

## Dataset Scope

| Item | Value |
|---|---:|
| Department analyzed | Produce |
| Produce products | 1,684 |
| Produce order-product rows | 409,087 |
| Produce baskets/orders | 96,927 |
| Full training orders used for cross-department analysis | 131,209 |
| Missing user_id values after merge | 0 |

Dataset files used:

```text
aisles.csv
departments.csv
products.csv
orders.csv
order_products__train.csv
```

The raw dataset is not included in this repository. See `data/README.md` for dataset setup instructions.

---

## Main Analyses

| Analysis Type | Description |
|---|---|
| Statistical Analysis 1 | Produce product distribution by aisle |
| Statistical Analysis 2 | Top 10 most purchased Produce products |
| Statistical Analysis 3 | Produce purchase timing by day of week and hour of day |
| Pattern Mining 1 | Product-to-product FP-Growth association rules |
| Pattern Mining 2 | Aisle-to-aisle FP-Growth association rules |
| Pattern Mining 3 | Cross-department FP-Growth association rules involving Produce |
| Extra Credit | K-means clustering of Produce shopping styles |

---

## Key Findings

- Produce products were concentrated in a few dominant aisles, especially packaged vegetables/fruits, fresh vegetables, and fresh fruits.
- Banana and Bag of Organic Bananas dominated Produce purchases.
- Produce purchase activity was strongest during daytime shopping hours, especially around 14:00-15:00.
- Product-level association rules showed recurring co-purchase patterns involving bananas, berries, avocados, spinach, and lemons.
- Aisle-level rules showed strong relationships between fresh vegetables, fresh fruits, and packaged vegetables/fruits.
- Cross-department rules showed Produce was strongly linked with dairy/eggs, beverages, snacks, frozen, and pantry items.
- Extra-credit clustering showed that Produce appears in multiple shopping styles: Produce-focused trips, small mixed-basket trips, and large grocery trips.

---

## Methods Used

| Method | Purpose |
|---|---|
| Data cleaning and joins | Combined products, departments, aisles, orders, and order-product records |
| Exploratory data analysis | Measured Produce structure, demand, and purchase timing |
| Data visualization | Communicated product, aisle, timing, and clustering patterns |
| FP-Growth | Mined frequent itemsets efficiently from transaction baskets |
| Association rule mining | Generated product, aisle, and department-level rules |
| K-means clustering | Identified Produce shopping-style segments |

---

## Pattern Mining Thresholds

| Analysis | Support Count Threshold | Confidence Threshold | Reason |
|---|---:|---:|---|
| Product-to-product rules | 500 | 0.10 | Kept meaningful product patterns without including too many rare rules |
| Aisle-to-aisle rules | 1,000 | 0.10 | Aisle patterns are broader and more frequent, so stricter support was appropriate |
| Cross-department rules | 1,000 | 0.05 | Cross-department rules are broader and naturally weaker, so lower confidence was appropriate |

---

## Example Results

### Product-to-Product Rules

| Rule | Support Count | Support | Confidence |
|---|---:|---:|---:|
| Organic Strawberries -> Bag of Organic Bananas | 3,074 | 0.0317 | 0.2822 |
| Organic Hass Avocado -> Bag of Organic Bananas | 2,420 | 0.0250 | 0.3318 |
| Organic Baby Spinach -> Bag of Organic Bananas | 2,236 | 0.0231 | 0.2285 |
| Organic Avocado -> Banana | 2,216 | 0.0229 | 0.2991 |
| Large Lemon -> Banana | 2,158 | 0.0223 | 0.2653 |

### Aisle-to-Aisle Rules

| Rule | Support Count | Support | Confidence |
|---|---:|---:|---:|
| fresh vegetables -> fresh fruits | 42,949 | 0.4431 | 0.7258 |
| fresh fruits -> fresh vegetables | 42,949 | 0.4431 | 0.5950 |
| packaged vegetables fruits -> fresh fruits | 37,694 | 0.3889 | 0.7500 |
| fresh fruits -> packaged vegetables fruits | 37,694 | 0.3889 | 0.5222 |
| packaged vegetables fruits -> fresh vegetables | 33,112 | 0.3416 | 0.6589 |

### Cross-Department Rules

| Rule | Support Count | Support | Confidence |
|---|---:|---:|---:|
| produce -> dairy eggs | 71,356 | 0.5438 | 0.7362 |
| produce -> beverages | 44,893 | 0.3421 | 0.4632 |
| produce -> snacks | 44,389 | 0.3383 | 0.4580 |
| produce -> frozen | 41,264 | 0.3145 | 0.4257 |
| produce -> pantry | 39,075 | 0.2978 | 0.4031 |

---

## Extra-Credit Analysis

The extra-credit portion used **K-means clustering** to identify shopping styles among orders that contained Produce.

The clustering used features such as:

- Number of Produce items in the order
- Total number of items in the order
- Number of unique departments
- Number of unique Produce aisles
- Produce share of the total basket

The analysis identified three main shopping styles:

| Cluster | Description |
|---|---|
| Produce-focused trips | Orders where Produce made up the largest share of the basket |
| Small mixed-basket trips | Smaller orders where Produce appeared with other grocery categories |
| Large mixed grocery trips | Larger orders across multiple departments that also included Produce |

---

## Repository Structure

```text
COMP541-Data-Mining-Final-Project/
├── README.md
├── Final_Project.ipynb
├── Report.pdf
├── Project_Presentation.pptx
├── requirements.txt
├── .gitignore
└── data/
    └── README.md
```

---

## Installation

### 1. Clone the repository

```bash
git clone https://github.com/LernikAvetisyan/COMP541-Data-Mining-Final-Project.git
cd COMP541-Data-Mining-Final-Project
```

### 2. Create and activate a virtual environment

```bash
python -m venv .venv
```

Windows PowerShell:

```powershell
.venv\Scripts\Activate.ps1
```

macOS/Linux:

```bash
source .venv/bin/activate
```

### 3. Install dependencies

```bash
pip install -r requirements.txt
```

### 4. Add dataset files

Place the required Instacart CSV files inside a local `data/` folder. See `data/README.md`.

### 5. Open the notebook

```bash
jupyter notebook Final_Project.ipynb
```

---

## Files Included

| File | Purpose |
|---|---|
| `Final_Project.ipynb` | Main Jupyter Notebook containing the analysis and code |
| `Report.pdf` | Final written report |
| `Project_Presentation.pptx` | Class presentation slides |
| `README.md` | Project overview and documentation |
| `requirements.txt` | Python dependencies |
| `data/README.md` | Dataset setup instructions |

---

## Resume Summary

Completed a COMP 541 data mining project analyzing 409,087 Instacart Produce order-product records and 96,927 Produce baskets. Applied statistical analysis, visualization, FP-Growth association rule mining, cross-department rule mining, and K-means clustering to identify purchasing patterns, product relationships, shopping-time behavior, and Produce shopping-style segments.

---

## Disclaimer

This project was completed for educational and portfolio purposes as part of COMP 541: Data Mining. The dataset is used for analysis only, and the repository does not include raw Instacart data files.
