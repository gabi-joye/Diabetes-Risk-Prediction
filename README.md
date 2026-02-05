# Diabetes-Risk-Prediction

**Dataset Overview**

This dataset contains signs and symptoms data for patients who are either newly diabetic or at risk of developing diabetes. The features include:

Age

Gender

Polyuria

Polydipsia

Sudden weight loss

Weakness

Polyphagia

Genital thrush

Visual blurring

Itching

Irritability

Delayed healing

Partial paresis

Muscle stiffness

Alopecia

Obesity

The target variable, Class, indicates whether a patient is diabetic or non-diabetic. All features are binary except for Age, which is numerical.

A Random Forest machine learning model was chosen for this project because it performs well with binary features and is effective at capturing non-linear relationships between symptoms.

**Exploratory Data Analysis (EDA)**

The project began with exploratory data analysis to understand the structure and quality of the dataset. This included reviewing the head and tail of the data, examining the dataset’s shape, and inspecting column data types and missing values.

From this analysis, it was determined that the dataset contains no missing values. However, aside from the Age column (integer), all other features were stored as object types, which required preprocessing. A class distribution visualization was also created to evaluate whether the dataset was balanced.

The initial class distribution showed that the dataset was somewhat imbalanced, with:

61.53% diabetic

38.46% non-diabetic

**Data Preprocessing**

Although no missing values were present, multiple duplicate rows were identified. These were removed using df.drop_duplicates(). After removing duplicates, the class distribution shifted to:

68.92% diabetic

31.07% non-diabetic

All binary categorical features were then encoded using sklearn’s LabelEncoder, converting them into 1s and 0s. Since a tree-based model was used, feature scaling was not required for the Age column.

**Model Training**

The dataset was split into 75% training data and 25% testing data. The Class column was used as the target variable (y), while all other features were used as predictors (X).

A RandomForestClassifier from scikit-learn was trained with a random_state of 42 to ensure reproducibility.

**Model Evaluation**

Model performance was evaluated using several classification metrics. Although accuracy can be misleading with imbalanced datasets, it still provides a useful baseline for performance. A confusion matrix was also created to visualize prediction outcomes.

Evaluation Metrics:

Accuracy: 93.65%

Precision: 0.93

Recall: 0.98

F1 Score: 0.95

These results indicate that the model performs very well, particularly in identifying diabetic patients, which is critical in medical prediction tasks where false negatives can be costly.


**Results & Conclusion**

The Random Forest model demonstrated strong performance in predicting diabetes based on patient symptoms. With an accuracy of 93.65%, the model correctly classified the majority of cases despite the dataset being moderately imbalanced. More importantly, the model achieved a recall of 0.98, indicating that it successfully identified nearly all diabetic patients. This is especially critical in a healthcare context, where failing to detect a positive case can have serious consequences.

The precision score of 0.93 suggests that most patients predicted as diabetic were correctly classified, while the F1 score of 0.95 reflects a strong balance between precision and recall. Together, these metrics show that the model not only performs well overall but also maintains reliability across both false positives and false negatives.

Overall, the Random Forest model proved to be a suitable choice for this classification task due to its ability to handle binary features and capture non-linear relationships between symptoms. While the results are promising, future improvements could include hyperparameter tuning, cross-validation, and experimenting with additional models to further validate performance. Additionally, techniques such as class weighting or resampling could be explored to address class imbalance more effectively.
