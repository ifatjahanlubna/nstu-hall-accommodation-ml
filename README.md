# Impact of Limited Hall Accommodation on Academic Performance and Wellbeing of NSTU Students

Machine learning analysis of how limited hall accommodation affects CGPA and living satisfaction of NSTU students, using survey data and six classification models.

`Python · Pandas · Scikit-learn · XGBoost · Matplotlib · Seaborn`

This is my 3rd-year project at Noakhali Science and Technology University (NSTU).

## About the project

NSTU does not have enough hall seats for all students, so many students live in messes or rented rooms outside the campus. I wanted to see whether a student's accommodation and living conditions can be used to predict their CGPA and how satisfied they are with their living situation.

I collected the data with a survey form and built the models in Python.

## Dataset

- Collected by survey from NSTU students
- 116 responses, 36 questions (accommodation type, distance, roommates, facilities, study environment, CGPA, satisfaction, etc.)
- The dataset is **not included** in this repository because it contains responses from real students.

## What I did

- Cleaned the survey data, filled missing values and fixed the department names
- Explored the data with charts and a correlation heatmap
- Label-encoded the categorical columns and split the data 80:20 into train and test sets
- Scaled the features and applied SMOTE on the training set only
- Trained six models: Decision Tree, Random Forest, XGBoost, Logistic Regression, SVM and KNN
- Compared them using accuracy, precision, recall, F1-score and confusion matrices

## Experiments

| Experiment | Target | Classes | Best model | Accuracy |
|---|---|---|---|---|
| 1 | CGPA | 3 | SVM | 62.50% |
| 2 | Living satisfaction | 5 | Random Forest / SVM | 41.67% |
| 3 | Living satisfaction (grouped: Low, Medium, High) | 3 | KNN | 66.67% |

Grouping living satisfaction into three classes improved the best accuracy from 41.67% to 66.67% in this experiment. The results can change with a different train-test split.

## Files

```
├── README.md
├── hall_accommodation_analysis.ipynb   # code, charts and results
└── report/
    └── NSTU_Hall_Accommodation_Report.pdf   # full project report
```

## How to run

1. Install the libraries:
   ```bash
   pip install pandas numpy matplotlib seaborn scikit-learn xgboost imbalanced-learn joblib
   ```
2. Put the survey file `hall_seat_MLdata.csv` in the same folder as the notebook (the data is not in this repo).
3. Open `hall_accommodation_analysis.ipynb` in Jupyter Notebook, VS Code or Colab and run the cells in order.

## Limitations

- Only 116 responses, so the results are not very stable.
- The results only describe this sample of NSTU students, not all students.
- The models show patterns, not cause and effect.
