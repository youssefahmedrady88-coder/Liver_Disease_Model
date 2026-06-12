# 🩺 Liver Disease Prediction Model

> **Early detection saves lives.** A supervised machine learning classifier that predicts the presence of liver disease from clinical and biochemical patient data — supporting medical professionals with an interpretable, data-driven diagnostic aid.

---

## 📌 Overview

Liver disease is a critical global health challenge where early and accurate diagnosis dramatically improves patient outcomes. This project applies a full supervised learning pipeline to a **10,000+ patient** clinical dataset to classify whether a patient is at risk of liver disease. The workflow spans exploratory data analysis, feature engineering, model training, hyperparameter tuning, and thorough evaluation — all within a reproducible Jupyter Notebook environment.

---

## ✨ Key Features

- **Complete ML pipeline** — raw CSV ingestion through to a tuned, evaluated classification model
- **Clinical EDA** — distribution analysis of biomarkers (bilirubin, enzymes, proteins), correlation matrices, class-imbalance inspection, and outlier handling
- **Feature engineering** — imputation of missing values, encoding of categorical variables (Gender), and normalization of skewed clinical measurements
- **Multi-model evaluation** — benchmarks classifiers including Logistic Regression, Decision Tree, Random Forest, and Gradient Boosting
- **Hyperparameter optimization** — `GridSearchCV` / `RandomizedSearchCV` tuned for F1-score to balance precision and recall on the positive (disease) class
- **Rich evaluation suite** — confusion matrix, classification report, ROC-AUC curve, and precision-recall analysis
- **Reproducible notebook** — fully documented `Liver_Disease_Solution.ipynb` with clear markdown explanations for each pipeline stage

---

## 🛠️ Tech Stack

| Category | Tool / Library |
|---|---|
| Language | Python 3.x |
| Data manipulation | `pandas`, `NumPy` |
| Visualization | `matplotlib`, `seaborn` |
| Machine learning | `scikit-learn` |
| Notebook environment | Jupyter Notebook |
| Version control | Git & GitHub |

---

## ✅ Prerequisites

Make sure the following are installed on your system:

- **Python 3.8+** — [python.org/downloads](https://www.python.org/downloads/)
- **pip** (bundled with Python)
- **Git** — [git-scm.com](https://git-scm.com/)
- **Jupyter Notebook or JupyterLab** (via pip or Anaconda)

---

## 🚀 Installation & Setup

```bash
# 1. Clone the repository
git clone https://github.com/youssefahmedrady88-coder/Liver_Disease_Model.git
cd Liver_Disease_Model

# 2. (Recommended) Create and activate a virtual environment
python -m venv venv
source venv/bin/activate        # macOS / Linux
venv\Scripts\activate           # Windows

# 3. Install required dependencies
pip install pandas numpy matplotlib seaborn scikit-learn jupyter

# 4. Launch Jupyter Notebook
jupyter notebook
```

Then open **`Liver_Disease_Solution.ipynb`** from the Jupyter file browser.

---

## 📖 Usage

### Running the notebook interactively

1. Open `Liver_Disease_Solution.ipynb` in Jupyter.
2. Run all cells in order (`Kernel → Restart & Run All`).
3. The notebook will:
   - Load `Training_Liver_Disease_Dataset.csv`
   - Perform EDA on clinical biomarker distributions
   - Preprocess data (imputation, encoding, scaling)
   - Train and benchmark multiple classifiers
   - Tune the best model with hyperparameter search
   - Output evaluation metrics, confusion matrix, and ROC curve

### Example: Running a prediction on new patient data

```python
import pandas as pd
import pickle

# Load your saved model (after running the notebook)
with open("liver_model.pkl", "rb") as f:
    model = pickle.load(f)

# Prepare a sample patient record (match training feature schema)
patient = pd.DataFrame([{
    "Age": 45, "Gender": "Male",
    "Total_Bilirubin": 1.2, "Direct_Bilirubin": 0.4,
    "Alkaline_Phosphotase": 180, "Alamine_Aminotransferase": 35,
    "Aspartate_Aminotransferase": 40, "Total_Protiens": 6.8,
    "Albumin": 3.5, "Albumin_and_Globulin_Ratio": 1.1
}])

prediction = model.predict(patient)
print("Liver disease prediction:", "Positive" if prediction[0] == 1 else "Negative")
```

---

## 📁 Repository Structure

```
Liver_Disease_Model/
├── Training_Liver_Disease_Dataset.csv   # Raw clinical dataset (10,000+ records)
├── Liver_Disease_Solution.ipynb         # Main Jupyter Notebook (full pipeline)
└── README.md                            # This file
```

---

## 🤝 Contributing

Contributions, improvements, and bug reports are welcome!

1. Fork the repository
2. Create a feature branch: `git checkout -b feature/your-feature-name`
3. Commit your changes: `git commit -m "Add: your descriptive message"`
4. Push to your branch: `git push origin feature/your-feature-name`
5. Open a Pull Request describing your changes

Please keep code clean, well-commented, and consistent with the existing notebook style. Clinical domain accuracy matters — please cite sources for any medical claims added to documentation.

---

## ⚠️ Disclaimer

This model is a research and educational tool. It is **not** intended for clinical diagnosis or to replace professional medical judgment. Always consult a qualified healthcare professional for medical decisions.

---

## 📜 License

This project is licensed under the **MIT License** — see the [LICENSE](LICENSE) file for details.

---

## 👤 Author

**Youssef Ahmed Rady**
Junior AI Engineer — B.Sc. Electronics & Communication Engineering, Helwan University

[![LinkedIn](https://img.shields.io/badge/LinkedIn-Connect-blue?logo=linkedin)](https://www.linkedin.com/in/youssef-ahmed-rady)
[![GitHub](https://img.shields.io/badge/GitHub-Profile-black?logo=github)](https://github.com/youssefahmedrady88-coder)
[![Email](https://img.shields.io/badge/Email-Contact-red?logo=gmail)](mailto:youssefahmedrady88@gmail.com)
