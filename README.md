# 📘 CompBio_Day_03.ipynb

## 🧪 Project Overview  
Implements a **machine learning workflow** for predicting **active drug candidates** targeting **AmpC beta-lactamase (PBP3, PDB ID: 1L2S)**. The workflow includes **data preprocessing, feature selection, model training, and evaluation**.

---

## 📂 Dataset  
- **File:** `ampc.csv`  
- **Description:** Molecular descriptors of chemical compounds.  
- **Target Variable (`Name`)**:  
  - `1` → Active compounds (`act1`, `ac1`)  
  - `0` → Inactive compounds (`decoy1`)  

---

## 🔄 Workflow Breakdown  

### 1️⃣ Data Preprocessing  
✔ Convert categorical labels (`Name`) to numerical values.  
✔ Drop constant features.  
✔ Handle missing values (filled with median values).  
✔ Standardize numerical features.  
✔ Apply SMOTE for handling class imbalance.  
✔ Split data into **80% training** and **20% testing**.

### 2️⃣ Feature Selection & Visualization  
✔ Compute **correlation matrix** to identify redundant features.  
✔ Drop highly correlated features (`correlation > 0.95`).  
✔ Use **pairplot** to analyze feature relationships.  

### 3️⃣ Machine Learning Model  
✔ Train a **RandomForestClassifier**.  
✔ Optimize model hyperparameters:  
   - `n_estimators=100`  
   - `max_depth=10`  
   - `min_samples_split=5`  
✔ Evaluate feature importance with **SHAP analysis**.  

### 4️⃣ Model Evaluation  
✔ Compute **precision, recall, AUC score**.  
✔ Visualize **confusion matrix, ROC curve, and feature importance**.  

---

## 📊 Results  
| **Metric**       | **Training Set** | **Testing Set** |
|-----------------|---------------|---------------|
| **Accuracy**    | 97.63%        | 86.4%        |
| **Precision**   | 87.2%         | 86.4%        |
| **Recall**      | 85.7%         | 85.0%        |
| **AUC Score**   | 91.0%         | 89.2%        |

✅ **Top Features Contributing to Predictions:**  
1️⃣ `vdw(i=6_j=12_s=1_^=100_c=8)`  
2️⃣ `gauss(o=3_w=2_c=8)`  
3️⃣ `non_hydrophobic(g=0.5_b=1.5_c=8)`  
4️⃣ `repulsion(o=0_c=8)`  
5️⃣ `num_heavy_atoms`  

---

## 🚀 How to Run the Notebook  

### 1️⃣ Install Dependencies  
```bash
pip install -r requirements.txt
