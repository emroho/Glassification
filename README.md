# Glass Classification

A data science project that uses the chemical composition of glass to predict its type. The project includes exploratory data analysis (EDA), a multi-classifier comparison, accuracy metrics, and an interactive prediction widget.

---

## 📋 Problem Statement

Given nine chemical attributes of a glass sample, classify it into one of six observable glass types:

| Code | Glass Type |
|------|-----------|
| 1 | Building Windows – Float Processed |
| 2 | Building Windows – Non-Float Processed |
| 3 | Vehicle Windows – Float Processed |
| 4 | Vehicle Windows – Non-Float Processed *(absent from dataset)* |
| 5 | Containers |
| 6 | Tableware |
| 7 | Headlamps |

No encoding is required because all feature values are numerical.

---

## 📂 Repository Structure

```
GlassClassification/
├── data/
│   └── glass.csv              # UCI Glass Identification dataset (214 samples)
├── notebooks/
│   └── GlassClassification.ipynb  # Main analysis & modelling notebook
└── README.md
```

---

## 📊 Dataset

**Source:** [UCI Machine Learning Repository – Glass Identification Data Set](https://archive.ics.uci.edu/ml/datasets/glass+identification)

| Attribute | Description |
|-----------|-------------|
| RI | Refractive Index |
| Na | Sodium (weight % in oxide) |
| Mg | Magnesium |
| Al | Aluminum |
| Si | Silicon |
| K | Potassium |
| Ca | Calcium |
| Ba | Barium |
| Fe | Iron |
| Type | Glass type (target, codes 1-7) |

- **214** total samples
- **9** numerical features
- **6** distinct glass types present (type 4 is absent)

---

## 🔬 Notebook Walkthrough

The notebook (`notebooks/GlassClassification.ipynb`) covers:

1. **Setup & Imports** – All required libraries
2. **Data Loading** – Read CSV and map type codes to descriptive labels
3. **Exploratory Data Analysis**
   - Dataset overview and descriptive statistics
   - Class distribution (bar chart + pie chart)
   - Feature distributions (histograms)
   - Feature distributions by glass type
   - Correlation heatmap
   - Box plots by glass type
4. **Data Preprocessing** – Train/test split (80/20, stratified) and feature scaling
5. **Model Training** – Four classifiers compared:
   - Random Forest
   - Gradient Boosting
   - Support Vector Machine (RBF kernel)
   - K-Nearest Neighbours
6. **Model Evaluation**
   - Cross-validation and test accuracy comparison
   - Classification report (precision, recall, F1-score)
   - Confusion matrix
   - Feature importance (Random Forest)
7. **Prediction Helper** – `predict_glass_type()` function with label output
8. **Interactive Widget** – Slider-based UI (ipywidgets) for real-time predictions
9. **Summary** table

---

## 🚀 Getting Started

### 1. Open PowerShell and go to the project folder

```powershell
cd C:\Users\emmah\Downloads\CMSE492\GlassClassification
```

### 2. Create the virtual environment

```powershell
py -3 -m venv .venv
```

### 3. If activation is blocked, allow scripts for this session only

```powershell
Set-ExecutionPolicy -Scope Process -ExecutionPolicy Bypass
```

### 4. Activate the virtual environment (PowerShell)

```powershell
.\.venv\Scripts\Activate.ps1
```

### 5. Upgrade pip

```powershell
python -m pip install --upgrade pip
```

### 6. Install dependencies

```powershell
pip install -r requirements.txt
```

### 7. Run the notebook

```powershell
jupyter notebook notebooks\GlassClassification.ipynb
```

> **Tip:** If you use classic Jupyter Notebook and widgets do not appear, run:
> ```powershell
> jupyter nbextension enable --py widgetsnbextension
> ```

---

## 📈 Models & Metrics

All four classifiers are evaluated with:
- **5-fold cross-validation accuracy** on the training set
- **Test set accuracy** on the held-out 20% split
- Full **classification report** (precision / recall / F1 per class)
- **Confusion matrix** visualisation
- **Feature importance** from the Random Forest model

The best-performing model is selected automatically and used for the interactive prediction widget.

---

## 🖥️ Interactive Widget

The notebook includes an `ipywidgets` panel with sliders for each chemical attribute. Click **Predict Glass Type** to see the predicted glass category in real time — no code changes needed.

---

## 📄 License

Dataset: UCI Machine Learning Repository (public domain).  
Code: MIT License.
