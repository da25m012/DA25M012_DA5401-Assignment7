# DA25M012_DA5401-Assignment7

---

##  Author

**Name** : G Ch V Sairam  
**Roll Number:** DA25M012  
Department : DSAI, M.Tech

---

##  Objective

The goal of this assignment is to **train and evaluate multiple classification models** on a multi-class dataset and compare their performance using advanced evaluation metrics such as:

* **Accuracy**
* **Weighted F1-score**
* **ROC-AUC (Macro-Averaged)**
* **PRC-AP (Macro-Averaged)**

In addition, the study includes the construction of a **deliberately poor (Flipped) model** to understand model behavior when predictions are systematically incorrect.

---

##  Dataset and Output Classes

The dataset used consists of **multi-class labels** with the following class set:

```
Output Classes: {1, 2, 3, 4, 5, 7}
```

The data was already split into **training** and **test sets**.
Feature scaling was applied.

---

##  Models Evaluated

| **Category**      | **Model**                       |
| :---------------- | :------------------------------ |
| Tree-based Models | Random Forest                   |
|                   | XGBoost                         |
|                   | Decision Tree                   |
| Linear Models     | Logistic Regression             |
|                   | SVC (Support Vector Classifier) |
| Instance-based    | KNN (k-Nearest Neighbors)       |
| Probabilistic     | Gaussian Naive Bayes            |
| Baseline          | Dummy Classifier                |
| Experimental      | Flipped Model                   |

---

##  Evaluation Metrics

All models were evaluated on the test set using:

* **Accuracy:** Proportion of correctly classified samples.
* **Weighted F1-score:** Harmonic mean of precision and recall, accounting for class imbalance.
* **Macro-Averaged ROC-AUC:** Area under the ROC curve averaged equally across all classes.
* **Macro-Averaged PRC-AP:** Area under the Precision-Recall curve, macro-averaged.

---

##  Results Summary

| Model                   | Accuracy | Weighted F1 |  Macro AUC |  Macro AP  |
| :---------------------- | :------: | :---------: | :--------: | :--------: |
| **Random Forest**       |  0.9130  |    0.9112   | **0.9901** | **0.9518** |
| **XGBoost**             |  0.9070  |    0.9055   |   0.9896   |   0.9498   |
| **SVC**                 |  0.8965  |    0.8982   |   0.9881   |   0.9266   |
| **KNN**                 |  0.8910  |    0.8895   |   0.9837   |   0.9357   |
| **Decision Tree**       |  0.8460  |    0.8457   |   0.9612   |   0.8620   |
| **Gaussian NB**         |  0.7965  |    0.8036   |   0.9553   |   0.8454   |
| **Logistic Regression** |  0.8400  |    0.8448   |   0.9751   |   0.7907   |
| **Dummy**               |  0.2305  |    0.0864   |   0.5000   |   0.2350   |
| **Flipped Model**       |  0.1250  |    0.1319   |   0.4991   |   0.2050   |


---

##  Model Ranking Summary

| **Metric**          | **Rank 1**    | **Rank 2** | **Rank 3** | **Rank 4** | **Rank 5**          | **Rank 6**          | **Rank 7**          | **Rank 8**    | **Rank 9**    |
| :------------------ | :------------ | :--------- | :--------- | :--------- | :------------------ | :------------------ | :------------------ | :------------ | :------------ |
| **Weighted F1**     | Random Forest | XGBoost    | SVC        | KNN        | Decision Tree       | Logistic Regression | Gaussian NB         | Flipped Model | Dummy         |
| **ROC-AUC (Macro)** | Random Forest | XGBoost    | SVC        | KNN        | Logistic Regression | Decision Tree       | Gaussian NB         | Dummy         | Flipped Model |
| **PRC-AP (Macro)**  | Random Forest | XGBoost    | KNN        | SVC        | Decision Tree       | Gaussian NB         | Logistic Regression | Dummy         | Flipped Model |

---

##  Observations and Insights

1. **Random Forest and XGBoost** achieved the highest overall performance across all metrics.
   Their ensemble nature effectively captures non-linear relationships and class boundaries.

2. **SVC and KNN** also performed competitively, but are more sensitive to data scaling.

3. **Logistic Regression** lagged slightly due to its linear decision boundaries.

4. **Decision Tree** performed worse than Random Forest, illustrating the benefit of ensembling.

5. **Dummy Classifier** and **Flipped Model** serve as **lower baselines**:

   * Dummy represents random or majority class guessing.
   * Flipped Model shows that systematic label inversion can yield **AUC < 0.5**, indicating inverse predictive power.

---

##  Conclusion

* Ensemble models like **Random Forest** and **XGBoost** remain the top-performing choices for this dataset.
* ROC-AUC and PRC-AP give deeper insights than accuracy alone, especially under class imbalance.
* The inclusion of a **Flipped Model** provides an excellent educational contrast, demonstrating how metrics like AUC reflect true vs. inverse discrimination capability.

---

##  File Description

| **File**                            | **Description**                                                                           |
| :---------------------------------- | :---------------------------------------------------------------------------------------- |
| `DA5401_Assignment7_DA25M012.ipynb` | Main notebook with all preprocessing, model training, evaluation, and visualization code. |
| `README.md`                         | Summary and analysis.                                                                     |

---

Would you like me to generate this as an actual downloadable **`README.md` file** (so you can submit or include it with your `.ipynb`)?

