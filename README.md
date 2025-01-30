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

## 📌 AmpC Protein Background  

### 1️⃣ What is AmpC?  
- **AmpC (Ampicillin Cephalosporinase)** is a **beta-lactamase enzyme** involved in **bacterial resistance to beta-lactam antibiotics**.
- It refers to the **crystal structure of Penicillin Binding Protein (PBP3)**.

### 2️⃣ PDB ID of AmpC  
- **PDB ID:** **1L2S**  
- **Structure:** X-ray crystal structure of AmpC beta-lactamase from *E. coli* in complex with a DOCK-predicted non-covalent inhibitor.  
- **Source:** [RCSB PDB - 1L2S](https://www.rcsb.org/structure/1L2S)  

### 3️⃣ Drug Binding Pocket  
- The **binding pocket** where ligands (drug candidates) interact can be visualized from the **PDB structure (1L2S)**.
- ![Binding pocket](https://drive.google.com/uc?export=view&id=1QATymwgdhWrkI0DuX2ToOqAiw6_yaGNL)

### 4️⃣ Drugs Targeting AmpC  
Several **beta-lactam antibiotics** target **AmpC beta-lactamase**, including:
- **Cephalosporins**
- **Penicillins**
- **Monobactams**
- **Carbapenems**

📌 **References:**
- [Penicillin-binding proteins: Master builders and breakers of bacterial cell walls](https://journals.asm.org/doi/10.1128/aac.01548-23)  
- [β-Lactam Resistance in ESKAPE Pathogens](https://www.mdpi.com/2218-273X/11/7/1057)  

### 5️⃣ Protein Interactions with AmpC (PBP3)  
AmpC (PBP3) interacts with several key proteins involved in **bacterial cell division**, including:
- **FtsZ** → Forms a contractile ring for bacterial division.  
- **FtsA** → Links FtsZ to the cytoplasmic membrane.  
- **FtsW** → Works with PBP3 to synthesize new bacterial cell wall components.  

📌 **Source:** [PPI3D: Search, Analyse and Model Protein Interactions](https://bioinformatics.lt/ppi3d)  

### 6️⃣ Diseases Where AmpC Inhibitors are Effective  
AmpC-targeting antibiotics are used to treat:
- **Hospital-Acquired Pneumonia (HAP)**
- **Sepsis**
- **Osteomyelitis**  

📌 **References:**
- [Ceftazidime-Avibactam for Treatment of Gram-Negative Infections](https://journals.asm.org/doi/10.1128/aac.01548-23)  

### 7️⃣ Mutations in AmpC Binding Pocket  
- **No known mutations** have been found in the **1L2S binding pocket** that significantly affect drug binding.  

📌 **Source:** [RCSB PDB - 1L2S](https://www.rcsb.org/structure/1L2S)  

---


