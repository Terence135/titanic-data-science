# titanic-data-science
An ongoing Titanic data-science learning notebook

## Pandas practice — 20 September 2026

Today's practice focused on choosing the right output shape for a question:

- Use grouped summaries such as `mean()` or `agg()` for one result per group.
- Use `transform()` when each original passenger needs their group's value for a comparison.
- Use `idxmax()` to find row labels, then `.loc` to retrieve the corresponding passengers.

Applied these ideas to class-level survival summaries, the highest-paying female passenger in each class, and fare and age comparisons against group medians. Also practised calculating missing-age percentages with Boolean indicators and reshaping group summaries with `unstack()`.

A useful habit to reinforce: calculate group statistics before filtering the comparison rows, and check the requested statistic, sort direction, and output size.
