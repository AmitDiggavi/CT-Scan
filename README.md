**CT Slice Localization Using Machine Learning**

**Overview:**

This project predicts the relative axial location of CT slices using 384 Bone and Air spatial features across more than 53,000 CT slices.
The analysis included exploratory data analysis, feature correlation, PCA, and comparison of multiple regression models.

**Tools used:**
Python, Pandas, NumPy, Matplotlib, scikit-learn, PCA, Modeling

**Dataset:**

Each CT slice contains:
- 240 Bone features
- 144 Air features
- patientId
- reference target value

The Bone and Air values are extracted spatial descriptors rather than raw CT image pixels.

**Analysis:**

EDA showed that Bone and Air feature patterns change across axial positions. Correlation analysis found that predictive information is distributed across many features rather than one dominant feature.
PCA reduced the 384 features to two dimensions for visualization. PC1 and PC2 explained about 27% of total feature variance and showed visible structure related to axial location.

**Machine Learning:**
The following regression models were compared using patient-based train/test splitting to avoid data leakage:

<img width="360" height="157" alt="image" src="https://github.com/user-attachments/assets/a37c2be2-9b77-4db2-b78b-ebe47428818c" />

**Conclusion:**

Random Forest clearly performed best, achieving an R² of 0.916 and MAE of 2.696 on held-out patients.
The results suggest that Bone and Air features contain strong information about CT slice location and that the relationship is better captured by a nonlinear model than by linear regression.

