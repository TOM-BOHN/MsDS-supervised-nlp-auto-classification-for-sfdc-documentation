# MsDS-supervised-nlp-auto-classification-for-sfdc-documentation
DTSA 5506 - Project - Auto-Classifying Salesforce Cloud Documentation Using NLP &amp; Supervised Learning

## Abstract

Develop a natural language processing (NLP) model to automate the classification of Salesforce documentation across various product features and cloud services, such as Sales Cloud and Service Cloud. Using a range of supervised learning algorithms,explore the feasibility of reducing manual content tagging by automatically categorizing documentation based on textual content. By leveraging tools like BeautifulSoup and Selenium for data collection and employing machine learning techniques such as TF-IDF vectorization, Support Vector Machine (SVM), and Logistic Regression, create a comprehensive pipeline for classifying Salesforce documentation. The models were trained and evaluated on a custom dataset of over 1,400 documents, achieving validation accuracies as high as 99.32%. The best-performing model, a Linear SVM, demonstrated exceptional accuracy and generalization across multiple levels of classification tasks, ranging from high-level cloud categorization (L0) to more granular job-specific (L1) and feature-specific (L2) tagging. By automating the classification process, provide a scalable solution for improving documentation discoverability and consistency across Salesforce platforms, significantly reducing the manual tagging workload while enhancing the precision and reliability of content retrieval.

## Results and Findings

Across L0, L1, and L2, Linear SVM consistently proved to be the most effective model, maintaining high accuracy, precision, and recall. Other linear models like SGD and Ridge Classifier performed similarly well, while non-linear models, especially AdaBoost, showed weaker performance. Hyperparameter tuning further optimized model accuracy, demonstrating that linear models are particularly well-suited for classifying Salesforce documentation at different levels of granularity.

**Consistent Top Performers:**

Linear SVM consistently emerged as a top-performing model across all levels, achieving validation accuracies around 0.986. Whether classifying broad categories (L0), specific Jobs to Be Done (L1), or granular features (L2), Linear SVM with hyperparameter tuning performed at or near the top.
SGD Classifier and Ridge Classifier also performed strongly across L1 and L2, achieving similar high validation accuracies, reflecting the robustness of these linear models for different levels of classification complexity.

**High Accuracy Across Levels:**

At L0, the focus was on distinguishing between Sales Cloud and Service Cloud, and the top models achieved nearly perfect validation accuracy (0.993).
At L1 and L2, where the task is to classify more specific Jobs to Be Done and granular features, the best models maintained high accuracy, with validation accuracies remaining consistently high (around 0.986).

**SVC Models and Hyperparameter Tuning:**

In all cases, SVC with linear kernels yielded excellent results, with hyperparameter tuning (adjusting the C parameter) further optimizing performance.
For L0 and L1, different values of C (0.1, 1, 10) performed similarly well, achieving near-identical validation accuracy.
At L2, C=1 was the best performer, reflecting that this middle ground between lower (C=0.1) and higher (C=100) values yielded the best balance between regularization and performance.

**Robustness Across Classifications:**

The best-performing models demonstrated robustness across different classification granularities. At L0 (broad two-class classification), L1 (11 JTBD classes), and L2 (41 feature classes), the Linear SVM consistently achieved high precision, recall, and F1-scores, indicating generalization across multiple levels of complexity.

**Weaker Performance of Non-Linear Models:**

Non-linear models like XGBoost, Random Forest, and especially KNN and AdaBoost consistently underperformed compared to linear models. While XGBoost and Random Forest still provided competitive results, models like AdaBoost showed much lower validation accuracies, particularly at L1 and L2, where validation accuracy dropped to 0.229.
