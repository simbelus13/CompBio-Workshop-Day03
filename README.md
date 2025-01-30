# 📘 CompBio_Day_03.ipynb

## 🧪 Project Title  
**Machine Learning Pipeline for Drug Screening Against AmpC Protein**  

---

## 📖 Description  
Implements a **machine learning workflow** for predicting **active drug candidates** targeting **AmpC beta-lactamase (PDB ID: 1L2S)**. The workflow includes **data preprocessing, feature selection, model training, and evaluation**.

---

## 📂 Dataset  
- **File:** `ampc.csv`  
- **Description:** Molecular descriptors of chemical compounds.  
- **Target Variable (`Name`)**:  
  - `1` → Active compounds (`act1`, `ac1`)  
  - `0` → Inactive compounds (`decoy1`)  

---

## 🔄 Workflow Overview  

### 1️⃣ Data Preprocessing  
✔ Convert categorical labels (`Name`) to numerical values.  
✔ Drop constant features.  
✔ Handle missing values (filled with median values).  
✔ Standardize numerical features.  

### 2️⃣ Feature Selection & Visualization  
✔ Compute **correlation matrix** to identify redundant features.  
✔ Use **pairplot** to analyze feature relationships.  

### 3️⃣ Machine Learning Model  
✔ Train a **RandomForestClassifier**.  
✔ Use **SMOTE** to handle class imbalance.  
✔ Optimize model parameters.  

### 4️⃣ Model Evaluation  
✔ Compute **precision, recall, AUC score**.  
✔ Visualize **confusion matrix, ROC curve, and SHAP feature importance**.  

---

## 📊 Results  
- **Model Accuracy:** **86.4%**  
- **Top Features Contributing to Predictions:**  
  1️⃣ `vdw(i=6_j=12_s=1_^=100_c=8)`  
  2️⃣ `gauss(o=3_w=2_c=8)`  
  3️⃣ `non_hydrophobic(g=0.5_b=1.5_c=8)`  

---

## 🚀 How to Run the Notebook  

### 1️⃣ Install Dependencies  
```bash
pip install -r requirements.txt
