#  Machine Learning Model Comparison for Pediatric Genetic Disorder

## Problem Statement
Predicting genetic disorders is a complex task influenced by multiple genetic and environmental factors. With the increasing availability of genetic datasets, machine learning provides an opportunity to enhance diagnostic accuracy and early detection. However, selecting the most suitable model for such complex, multi-feature data remains a key challenge.
This project focuses on *evaluating and comparing the predictive performance* of three machine learning algorithms: *Support Vector Machine (SVM), **Random Forest, and **Decision Tree*  after thorough data cleaning and preprocessing, to identify which model delivers the most reliable predictions for *genetic disorder classification*.


## Tools & Libraries
- *Programming Language:* Python  
- *Libraries Used:* pandas, numpy, scikit-learn, matplotlib, seaborn  



## Key Findings from the Analysis

###  1. Model Performance Comparison

1. Model Performance Comparison
*Cross-Validation (F1-weighted scores):*  
- Decision Tree: 0.5151 ± 0.0215 (Best performance)  
- Random Forest: 0.4830 ± 0.0107 (Moderate performance)  
- SVM: 0.4670 ± 0.0037 (Most stable but lowest performance)  

*Single Test Split Results:*  
- SVM: 60.4% accuracy, ROC AUC = 0.515  
- Random Forest: 59.6% accuracy, ROC AUC = 0.525  
- Decision Tree: 51.7% accuracy, ROC AUC = 0.496


###  2. Dataset Characteristics
- *Total Patients:* 5,585 (3,381 alive, 2,204 deceased)  
- *Age Range:* Pediatric population (0–14 years), relatively uniform distribution  
- *Outcome Distribution:* 60.5% survivors, 39.5% non-survivors (moderate imbalance)

*Key Clinical Variables:*
- Genetic factors: Family inheritance patterns, maternal genetic markers  
- Clinical history: Previous pregnancies, blood cell counts, genetic disorder types  



###  3. Critical Clinical Insights

*Genetic Risk Factors*
- *Maternal Genetic History:* Strong predictor – higher mortality (60% vs 40% survival)  
- *Paternal Inheritance:* Less discriminative  
- *Blood Cell Count:* Minimal impact (median ~4.9 mcl)  
- *Mitochondrial Disorders:* Associated with more severe outcomes  
- *Multifactorial Disorders:* Lower prevalence; possible diagnostic underreporting  

*Age-Related Survival Patterns*
- Infants: 38% survival  
- Toddlers: 59% survival  
- Children/Adolescents: 58–60% survival  


##  Model Evaluation and Justification

###  *Decision Tree – Optimal Model*
- *Highest F1-weighted score (0.5151)* across cross-validation  
- *Handles minority class better* (recall = 0.39 for deceased patients)  
- *Clinically interpretable:* Decision rules and feature importance are transparent  
- *Balanced performance* without over-conservatism seen in SVM or Random Forest  

###  Why Not the Alternatives?
*SVM*
- Lowest cross-validation performance  
- Extremely poor recall for deceased patients (1%)  
- “Black-box” model → poor interpretability  
- Risky for clinical use due to missed high-risk cases  

*Random Forest*
- Moderate results, high computational cost  
- Low recall for minority class (5%)  
- Less interpretable and unnecessarily complex  


##  Recommendations for Future Work

Based on the findings of this analysis, the following improvements are *proposed for future iterations* of the model and dataset. These recommendations reflect analytical insights and practical steps to enhance model performance, clinical reliability, and generalizability.

### 1. Immediate Improvements (High Priority)
- *Address Class Imbalance:* Apply SMOTE (Synthetic Minority Oversampling), adjust class weights, and use cost-sensitive learning to better detect high-risk (deceased) patients.  
- *Enhance Feature Engineering:* Introduce new variables such as genetic interaction terms (maternal × paternal), age-risk interactions, and composite clinical risk scores.  
- *Explore Ensemble Methods:* Implement weighted voting, stacking, or boosting approaches (e.g., XGBoost, AdaBoost) to improve predictive stability and robustness.  

### 2. Advanced Improvements (Medium Priority)
- *Model Architecture Enhancement:* Experiment with Gradient Boosting, LightGBM, and Neural Network architectures for more complex pattern recognition.  
- *Data Enrichment:* Collect additional variables like treatment history, comorbidities, and biomarkers to improve feature discriminability and model accuracy.  
- *Longitudinal Tracking:* Incorporate temporal features to capture disease progression and treatment response over time.  

### 3. Validation and Deployment (Long-Term Goals)
- *External Validation:* Test models on independent hospital datasets or through multi-center collaborations to ensure real-world generalizability.  
- *Clinical Integration:* Gradually integrate the best-performing model into hospital workflows as a decision-support tool, with human oversight and periodic retraining.  
- *Continuous Monitoring:* Regularly evaluate model performance and update it with new patient data to maintain reliability and trustworthiness.

##  Limitations

### *Dataset Constraints*
- ROC AUC ≈ 0.5 → weak feature discriminability  
- Missing key clinical context (e.g., comorbidities, treatments, progression)  
- Single-institution data → limited generalizability  
- Possible selection and demographic bias  

### *Model Limitations*
- Decision Tree prone to overfitting and instability  
- All models struggle with class imbalance  
- Retrospective design → no causal inference  
- Binary outcomes (survival/death) lack nuanced patient trajectories  


##  Clinical Implementation Recommendations

### *Deployment Strategy*
1. *Phase 1:* Pilot testing with decision-support alerts  
2. *Phase 2:* Integration with hospital risk protocols  
3. *Phase 3:* Full deployment with continuous model retraining  

*Risk Mitigation:*
- Always maintain *human oversight*  
- Provide *confidence intervals* for predictions  
- Regularly *retrain* with new data  

*Success Metrics*
- Improved early detection of high-risk patients  
- Reduction in mortality rates  
- Model performance stability on new data  
- Clinician adoption and satisfaction  



##  Conclusions
This project demonstrates that the *Decision Tree model* offers the best combination of:
- *Performance* (F1-weighted: 0.5151)  
- *Interpretability* (clinically explainable logic)  
- *Minority class sensitivity*  

However, *dataset limitations* — particularly weak feature discriminability remain the main barrier to predictive accuracy (ROC AUC ≈ 0.5).  
Future work should prioritize *data enrichment, **feature engineering, and **external validation* to achieve clinically meaningful results.

*Recommended Next Steps:*
1. Deploy Decision Tree with SMOTE and ensemble improvements  
2. Expand data collection and feature design  
3. Validate externally before clinical integration  

*Target Performance:*  
Achieve F1-weighted > 0.65 and ROC AUC > 0.70  while maintaining model interpretability and clinical reliability  

---

##  Author
*Oluwatofunmi Fak-Adeniyi*  
 tofunmiadedayo2@gmail.com 
 [LinkedIn Profile](https://www.linkedin.com/in/oluwatofunmi-fak-adeniyi-584909260/)  
