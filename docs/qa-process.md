# QA process

Draft v0.1. How labels go from first pass to training-ready.

## Flow
```
Label  →  Review (sampled)  →  Approved  →  Export
              ↓
        Needs fix  →  back to labeler
```

## Sampling
- New labelers: review 100% of their first 50 images.
- After that: review a random 10–20% per labeler per batch.
- Always review: anything tagged `uncertain-id`, `borderline` or `occluded`.
- If a labeler's error rate in a batch is above 10%, review their whole batch.

## Agreement
- A fixed 5–10% of images are labeled by two people (overlap set).
- Cow ID: percentage of boxes with the same identity.
- BCS: percentage within ±0.25, plus mean absolute difference and Cohen's weighted kappa.
- Boxes: IoU ≥ 0.75 counts as a match.

## Error types to track
| Code | Meaning |
|---|---|
| `wrong-id` | Box assigned to the wrong cow |
| `missed-cow` | A visible cow has no box |
| `loose-box` | Box too large or cuts off the body |
| `bcs-off` | BCS more than 0.25 from the reviewer's score |
| `missing-flag` | Should have been flagged (blurry, occluded…) |

## Metrics dashboard (planned)
Throughput per labeler, review pass rate, agreement over time, error types by labeler, and guideline sections causing the most disagreement.
