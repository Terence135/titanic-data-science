# titanic-data-science
An ongoing Titanic data-science learning notebook

## Pandas practice — 20 September 2026

Today's practice focused on choosing the right output shape for a question:

- Use grouped summaries such as `mean()` or `agg()` for one result per group.
- Use `transform()` when each original passenger needs their group's value for a comparison.
- Use `idxmax()` to find row labels, then `.loc` to retrieve the corresponding passengers.

Applied these ideas to class-level survival summaries, the highest-paying female passenger in each class, and fare and age comparisons against group medians. Also practised calculating missing-age percentages with Boolean indicators and reshaping group summaries with `unstack()`.

A useful habit to reinforce: calculate group statistics before filtering the comparison rows, and check the requested statistic, sort direction, and output size.


## Model evaluation and feature engineering — 21 September 2026

Practised precision, recall, F1, support, and the effect of changing the survival decision threshold. Survivor-class results (rounded from the classification reports):

| Threshold | Precision | Recall | F1 |
|---|---:|---:|---:|
| 0.3 | 0.65 | 0.81 | 0.72 |
| 0.5 | 0.75 | 0.68 | 0.71 |
| 0.7 | 0.89 | 0.45 | 0.60 |

These are exploratory comparisons on the existing test split, not a final threshold-selection procedure. Future feature and model comparisons will use validation data; this repeatedly inspected test split is no longer an untouched final evaluation.

Inspected the 712 training passengers and four original features. Explored survival by family size using training rows only, created an `IsAlone` indicator, and added it to a copied training feature table (712 rows, five features). Practised selecting passengers with `df.loc[X_train.index]` and aligning a new column by passenger index.

Next: add `familySize` to the feature table, then set up validation and compare feature variants. No improved model has been trained yet.

## Validation and feature comparison — 24 September 2026

Set up a validation split from the training data and compared logistic-regression variants using the original features, `IsAlone`, `familySize`, and both engineered features. Learned that adding `IsAlone` alone left the metrics unchanged on this validation split, while adding both features increased precision from 0.69 to 0.72 but reduced recall from 0.67 to 0.65. Created grouped bar charts for recall and for precision/recall together, then recorded the interpretation in the notebook.

The current next experiment is to compare a decision tree with the original logistic-regression model using the same validation split.

## Pandas practice — 24 September 2026

Added [today's practice notebook](Pandas_Practice_2026-09-24.ipynb), preserving the saved exercise attempts and outputs. Practised filtering, grouped summaries, passenger selection with `idxmin`/`idxmax`, row-aligned statistics with `transform`, family-size categories, age bands, and title extraction.

This is work in progress, not a completed or fully reviewed solution set. Some calculations still need correction, and the rare-title exercise remains unfinished with a recorded error.
