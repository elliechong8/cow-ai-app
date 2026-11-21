# Cow AI

Labeling, QA and computer vision tools for dairy herds: identify individual cows from photos, score body condition, and build clean training data for livestock AI.

> Status: early prototype. The labeling app runs today; the backend and ML models are on the roadmap.

## What's here

| Folder | What it is | Status |
|---|---|---|
| [`apps/web`](apps/web) | Labeling UI: draw boxes, tag cows, match suggestions, herd view, export | ✅ Working prototype |
| [`apps/api`](apps/api) | Backend: herd, images, labels, review queue, auth | 🔜 Planned |
| [`ml/detection`](ml/detection) | Cow detector (YOLO) to pre-draw boxes | 🔜 Planned |
| [`ml/reid`](ml/reid) | Individual cow re-identification from coat patterns | 🔜 Planned |
| [`ml/bcs`](ml/bcs) | Body condition score prediction | 🔜 Planned |
| [`data`](data) | Dataset sources and import/conversion scripts | 🔜 Scripts planned |
| [`docs`](docs) | Labeling guidelines and QA process | 📝 Drafts |

## Quick start

```bash
cd apps/web
python3 -m http.server 8000
# open http://localhost:8000
```

No build step yet. Labels are saved in the browser; use **Export labels** to get JSON (bbox `[x, y, w, h]` in pixels) or a herd CSV.

## Roadmap

1. **Body condition score (BCS) labeling:** 1–5 scale in 0.25 steps, reference guide, optional keypoints
2. **Dataset import:** load COCO / YOLO annotations from public cow datasets
3. **Backend:** shared database + image storage, logins, labeler / reviewer / admin roles
4. **QA workflow:** review queue, approve / reject, spot-check sampling, inter-annotator agreement
5. **Model-assisted labeling:** detector proposes boxes, re-ID suggests identities, BCS model suggests scores
6. **More tasks:** lameness from video, behaviour labels, vaccination and treatment tracking

## Planned stack

- Web: React + TypeScript + Vite (migrating from the current single-file prototype)
- API: Supabase (Postgres, auth, storage) or FastAPI + Postgres
- ML: Python, Ultralytics YOLO, PyTorch

## Docs

- [Body condition scoring guidelines](docs/labeling-guidelines/bcs.md)
- [Cow ID labeling guidelines](docs/labeling-guidelines/cow-id.md)
- [QA process](docs/qa-process.md)
