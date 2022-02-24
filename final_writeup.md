# Migitating DDoS attacks and ensuring service availability
Nate DiRenzo

## Abstract
The goal of this project was to assess the viability of using a binary classification model to identify malicious vs. benign network traffic in the midst of a DDoS attack. If traffic was identified as malicious by the model, it would be blocked from accessing the services. If it was identified as legitimate, it would be allowed to access the services. Here, we evaluated how well various classification methods performed the task, and whether they are viable business solutions given our success metrics.
## Design
The design of this project was a bakeoff between various classification methods for best performance of the given task on the dataset. In terms of business use case, our goal was to 1) Minimize the amount of legitimate traffic misidentified as malicious (ideally to 0). And 2) Mitigate the effects of a DDoS attack by correctly identifying malicious traffic 90% of time or better. In statistical terms, Recall as close to 1.0 as possible, Precision >= .9, F2 as close to 1.0 as possible (used in model selection for ensembling).
## Data
The [dataset](https://www.unb.ca/cic/datasets/ddos-2019.html) is used with permission by the Canadian Institute for Cybersecurity. It contains 2.18 million network traffic logs with 80+ features for each. It is heavily imbalanced-- 99.3% of observations in the dataset are labelled malicious while .7% of the data is benign. The data was created in a simulation testbed by the cybersecurity institute, but reflects a real-world DDoS scenario where the vast majority of traffic a service sees would be malicious.

## Algorithms

*Data Wrangling*
1. Eliminating NaN/Infinity Values
2. Dropping unnecessary features such as I.P., Port
3. Coercing all data types into numeric
4. Encoding Label column

*Models*
  
- Logisitc Regression
- Random Forest with various sampling methods
- Gradient Boosting 
*Model Evaluation and Selection*
  
Dataset was split into 60/20/20 Train/Validation/Test split, and validation data was used to tune hyperparameters. Once final model selection had been made based on validation scores, final model was tested against test data. Data splits were reshuffled for each model. Model selection was driven by F2, Recall, and Precision score. Top models were evaluated using Voting and Stacked Classifier ensembling methods. Because we were working with fine margins, detailed confusion matrices for each model were also produced.

**Final Stacked Classifier Ensemble**

**Validation:**
   - F2: 1.0
   - Precision: 1.0
   - Recall: 1.0 

**Test**   
   - F2: .997  
   - Precision: 1.0 
   - Recall: .996

## Tools
- **Numpy**, **Pandas**, and **Dask** for data ingestion & manipulation.
- **Scikit-learn**, **Imbalanced-learn**, and **XGBoost** for modeling and evaluation
- **Matplotlib** and **Seaborn** for visualization

## Communication
See [PDF](https://github.com/NateDiR/DDoS_traffic_classification/blob/main/DDoS%20Classification%20Presentation.pdf) of slides.
