# Early-Detection-of-Pathological-Fetal-States-
I look at cardiotocogram (CTG) data (Ayres de Campos et al. (2000) SisPorto 2.0 A Program for Automated Analysis of Cardiotocograms. J Matern Fetal Med 5:311-318 (link)) assessing fetal health to build a machine learning model that can predict whether a fetus is in a pathological state

## Model
- XGBoost Classifier
-       max_depth=3,
        n_estimators=200,
        subsample=1.0,
        objective="multi:softprob",
        num_class=3,
        eval_metric="mlogloss",
        random_state=0, 
        min_child_weight=1, 
        reg_lambda=1, 
        colsample_bytree=1.0,
        gamma=0,
        learning_rate=0.1,
        reg_alpha = 0
- 10-fold Cross Validation
- Macro F1 score evaluation

## Results
- Accuracy: 0.88
- Macro F1: 0.80
- Pathological Recall: 0.82

## Findings
- The model performs strongly on normal cases.
- Most confusion occurs between normal and suspect.
- I made a unique metric to measure pathological recall specifically, and the model performed relatively strongly on this (0.82)
- I think the main area for further improvement is increasing recall for suspect cases as well, given these are cases we'd also want to pay special attention to
