# Structural Balance Analysis in Brain Networks
**Course:** Complex Networks and Graph Theory (2025)  
**Type:** Course Project  
**Author:** Alireza Haghparast 
**Paper Reference:** [Altered structural balance of resting-state networks in autism](https://doi.org/10.1038/s41598-020-80330-0)  

## 📖 Overview
This project replicates and extends the analysis from the paper  
*"Altered structural balance of resting-state networks in autism"*  
by interpreting resting-state functional MRI (rs-fMRI) connectivity through the lens of **Structural Balance Theory (SBT)**.

The original paper applied SBT to study signed brain networks in Autism Spectrum Disorder (ASD) versus control participants.  
Here, we replicate the methodology **using a different dataset** to evaluate the reproducibility of their results.

## 🎯 Objectives
- Construct **functional connectivity matrices** from fMRI `.1D` time series data
- Apply **Structural Balance Theory** to classify **triads** into four categories (T0, T1, T2, T3)
- Compute and compare:
  - Triad frequencies
  - Positive/negative link ratios
  - Network energy
- Compare results between **ASD** and **control** groups across **developmental stages**


## ⚙️ Methodology
1. **Data Loading**  
   - Load `.1D` time series files (time points × ROIs) for each subject.
2. **Connectivity Matrix Computation**  
   - Pearson correlation between ROIs.
   - Threshold and sign assignment for positive/negative links.
3. **Triad Classification**  
   - Using SBT definitions:
     - **T3 (+++):** Strongly balanced  
     - **T1 (+−−):** Weakly balanced  
     - **T2 (++−):** Strongly unbalanced  
     - **T0 (−−−):** Weakly unbalanced
4. **Energy Computation**  
   - Following the equation from the paper:
     \[
     U(N) = -\frac{\sum_{i<j<k} S_{ij}S_{jk}S_{ki}}{\binom{N}{3}}
     \]
5. **Statistical Analysis**  
   - Compare **group** and **group × age** interactions using ANCOVA.

## 📊 Results
- Positive and negative link proportions differ between groups.
- Triad distribution patterns follow similar trends to the original paper but vary in magnitude due to dataset differences.
- Energy metrics replicate the general developmental trends.

## 🛠 Requirements
- Python 3.9+
- NumPy
- Pandas
- Matplotlib / Seaborn
- Statsmodels

Install dependencies:
```bash
pip install numpy pandas matplotlib seaborn statsmodels
```

## 📚 References
1. Jalili, M. et al. *Altered structural balance of resting-state networks in autism*.  
   Scientific Reports 11, 196 (2021). DOI: [10.1038/s41598-020-80330-0](https://doi.org/10.1038/s41598-020-80330-0)
2. Complex Networks and Graph Theory course materials (2025)

---
