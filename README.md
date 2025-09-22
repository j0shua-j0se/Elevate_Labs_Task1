# Elevate_Labs_Task1
Here is a ready-to-commit README.md tailored to the internship Task 1 and the Titanic dataset.

# Titanic: Data Cleaning & Preprocessing (Task 1)

A complete, reproducible data cleaning and preprocessing pipeline for the Titanic dataset, covering exploration, imputation, encoding, scaling, and outlier visualization/removal as required by Task 1.

### Overview
This repository demonstrates a professional preprocessing workflow on the Titanic dataset, delivering an end-to-end notebook/script, saved visualizations, and a cleaned CSV suitable for downstream modeling.

### Dataset
- Input file path (Windows): C:\Users\OMEN\.cache\kagglehub\datasets\yasserh\titanic-dataset\versions\1\Titanic-Dataset.csv
- Output cleaned CSV: C:\Users\OMEN\.cache\kagglehub\datasets\yasserh\titanic-dataset\versions\1\Titanic-Dataset-Cleaned.csv
- Target column, if present: Survived

### What this implements
- Step 1: Import and exploration including shape, dtypes, null counts, and a missingness heatmap.  
- Step 2: Missing value handling using median for numeric and most frequent for categorical.  
- Step 3: Categorical encoding via OneHotEncoder with unknown-safe handling for robust pipelines.  
- Step 4: Feature scaling of numeric columns using StandardScaler for normalization/standardization.  
- Step 5: Outlier visualization with boxplots and removal via 1.5×IQR capping, with before/after plots.  

### Key files
- Notebook or script implementing the five required steps, with clear, titled sections and inline visuals.  
- Generated plots: boxplots before and after capping for key numeric features (e.g., Age and Fare).  
- Cleaned CSV at the specified output path with fully numeric features and scaled continuous variables.  

### Environment
- Python 3.9+ recommended.  
- Libraries: pandas, numpy, seaborn, matplotlib, scikit-learn.  
- Create a virtual environment and install dependencies as needed.
- 
### Preprocessing details
- Missing values  
  - Numeric: median imputation to reduce sensitivity to skew.  
  - Categorical: most_frequent imputation to preserve mode categories.  
- Encoding  
  - OneHotEncoder with handle_unknown="ignore" to avoid errors on unseen categories.  
  - DataFrame conversion ensures a fully numeric table for modeling.  
- Scaling  
  - StandardScaler applied to continuous numeric features, not to target or ID columns.  
- Outliers  
  - Visualized via seaborn boxplots for clarity.  
  - Removed by winsorization-style capping using Tukey’s 1.5×IQR lower/upper fences.  

### Visual outputs
- Missingness Heatmap (raw and after imputation).  
- Boxplot Before Capping: Age and Fare.  
- Boxplot After Capping: Age and Fare.  
- Optional KDE overlays illustrating distribution changes after scaling.  

### Reproducibility
- Random seeds set where applicable.  
- Pipeline steps are deterministic given the same input file.  
- Paths are parameterized at the top of the code for easy adaptation.

### Optional baseline model
- A minimal Logistic Regression can be run after preprocessing to validate that features are numeric and the pipeline is usable.  
- This step is optional for Task 1 but useful for sanity checking the cleaned data.

### Known issues and tips
- OneHotEncoder API change: the sparse argument is removed in newer scikit-learn versions; the code avoids passing it and converts to dense arrays as needed.  
- If plots do not display in a notebook, ensure plt.show() is called and the inline backend is active.  
- If using a different dataset variant, verify target and column names and adjust lists accordingly.

### How to reproduce exactly
1) Update INPUT_PATH and OUTPUT_PATH at the top of the notebook or script.  
2) Run all cells/execute the script.  
3) Confirm plots are created under outputs/ and the cleaned CSV is written to the specified path.  

### Submission checklist
- Code runs top to bottom without errors.  
- All five steps are present with visual evidence for exploration and outlier handling.  
- Cleaned CSV saved at the specified output path.  
- Plots saved and rendered inline in the notebook.  
- This README included at the repository root.  

### License and acknowledgments
- This work is for educational purposes as part of a preprocessing task.  
- The dataset originates from the Titanic dataset hosted on KaggleHub via the specified local path.

### Main Output Preview
<img width="980" height="479" alt="BoxPlot_B4_Capping_Fare" src="https://github.com/user-attachments/assets/9747efeb-5525-4445-8a64-0a8ee7921cf1" />
<img width="978" height="479" alt="BoxPlot_B4_Capping_AGE" src="https://github.com/user-attachments/assets/d57d31e4-2291-4c11-9e03-9f0bf7078c16" />
<img width="995" height="493" alt="BoxPlot_After_Capping_Fare" src="https://github.com/user-attachments/assets/9bbbe8aa-86f6-4d87-a917-aba0ef20eb2a" />
<img width="989" height="488" alt="BoxPlot_After_Capping_Age" src="https://github.com/user-attachments/assets/bf7699bf-7a5f-44fe-9fe7-08114cc60d62" />


