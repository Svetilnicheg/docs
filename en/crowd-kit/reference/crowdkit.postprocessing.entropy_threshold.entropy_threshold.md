# entropy_threshold
`crowdkit.postprocessing.entropy_threshold.entropy_threshold` | [Source code](https://github.com/Toloka/crowd-kit/blob/v1.1.0/crowdkit/postprocessing/entropy_threshold.py#L13)

```python
entropy_threshold(
    answers: DataFrame,
    workers_skills: Optional[Series] = None,
    percentile: int = 10,
    min_answers: int = 2
)
```

Entropy thresholding postprocessing: filters out all answers by workers,


whos' entropy (uncertanity) of answers is below specified percentile.

This heuristic detects answers of workers that answer the same way too often, e.g. when "speed-running" by only
clicking one button.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`answers`|**DataFrame**|<p>Workers&#x27; labeling results. A pandas.DataFrame containing `task`, `worker` and `label` columns.</p>
`workers_skills`|**Optional\[Series\]**|<p>workers&#x27; skills. A pandas.Series index by workers and holding corresponding worker&#x27;s skill</p>

* **Returns:**

  pd.DataFrame

* **Return type:**

  DataFrame

**Examples:**

Fraudent worker always answers the same and gets filtered out.

```python
answers = pd.DataFrame.from_records(
    [
        {'task': '1', 'worker': 'A', 'label': frozenset(['dog'])},
        {'task': '1', 'worker': 'B', 'label': frozenset(['cat'])},
        {'task': '2', 'worker': 'A', 'label': frozenset(['cat'])},
        {'task': '2', 'worker': 'B', 'label': frozenset(['cat'])},
        {'task': '3', 'worker': 'A', 'label': frozenset(['dog'])},
        {'task': '3', 'worker': 'B', 'label': frozenset(['cat'])},
    ]
)
entropy_threshold(answers)
```
0    1         A  (dog)
2    2         A  (cat)
4    3         A  (dog)
