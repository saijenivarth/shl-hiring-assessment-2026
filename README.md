# SHL Hiring Assessment 2026 — Spoken English Grammar Scoring

Solution repository for the SHL Hiring Assessment 2026 grammar-scoring challenge.

## Best confirmed Kaggle result

**Public leaderboard score: 0.3819**

This is the score from our actual submission **`submission1.csv`**.

The previously mentioned **0.3814** score was from a separate random CSV upload used only as a leaderboard check and is **not** our solution result.

## Approach

The solution treats the task as continuous regression from spoken-English audio (0–5). The notebook combines:

- pretrained speech representations
- segment-level audio views
- acoustic/prosodic features
- leakage-safe out-of-fold regression
- ensemble/stacking
- validation and submission checks

The dataset contains 769 labelled training recordings and 216 evaluation recordings.

## Repository contents

- `solution.ipynb` — main documented solution notebook
- `README.md` — project overview
- `requirements.txt` — Python dependencies
- `SUBMISSION_STATUS.md` — verified leaderboard/submission status
- `.gitignore` — prevents accidental credential/cache uploads

## Submission format

The final prediction file must contain:

```text
filename,label
```

with:

- 216 rows
- the exact filename order from `test.csv`
- finite predictions
- predictions constrained to `[0, 5]`

## Reproducibility

Run the notebook in the SHL Kaggle environment with the competition dataset mounted at the expected input path. The notebook includes the required training RMSE and validation/report sections.

## Important

Do **not** upload private competition audio/data to a public repository unless SHL explicitly permits redistribution.

Do **not** upload Kaggle API credentials, tokens, or other secrets.

The exact `submission1.csv` file that achieved 0.3819 is not included unless that exact file is available. Do not substitute another candidate and label it as the 0.3819 submission.
