# Cow AI: notes for Claude Code

## What this is
A personal portfolio project (repo: `cow-ai/cow-ai-app`): labeling + QA platform and computer vision for dairy cows. Goal: internal-tool quality, i.e. real QA workflow, guidelines, exports in standard formats.

This is built from scratch. Do not copy code, data or docs from any employer project.

## Layout
- `apps/web/index.html`: the current prototype. Single file (HTML + CSS + JS), no build step.
- `apps/api/`: backend (not started).
- `ml/detection`, `ml/reid`, `ml/bcs`: model work (not started).
- `data/`: dataset docs and `scripts/` for converters. Raw data goes in `data/raw/` (gitignored).
- `docs/`: labeling guidelines and QA process. Keep these in sync with what the app supports.

## Web app internals
- State: `S = {images, boxes, cows, cur}`, saved to localStorage key `herd-labeler-v1`.
- Boxes are in image pixel coordinates. Each box has `sig` (16x10 binary coat pattern + mean colour) for match suggestions and `thumb` (JPEG crop).
- Demo herd/photos are drawn by code (`drawCow`, `scene`, `loadDemo`).
- Design: Holstein black/white, ear-tag yellow `#f6c90e`; Barlow Condensed (tag numbers) + Barlow. 44px touch targets, visible focus.

## Next tasks (in order)
1. BCS labeling in the web app: per-box score 1–5 in 0.25 steps, optional keypoints (hooks, pins, tailhead), reference panel from `docs/labeling-guidelines/bcs.md`, BCS in JSON/CSV export.
2. `data/scripts/coco_to_cowai.py`: convert COCO JSON / YOLO txt into the app's import format; add an Import button to the web app.
3. Migrate `apps/web` to React + TypeScript + Vite once step 1–2 land.
4. Backend in `apps/api` (Supabase or FastAPI + Postgres): auth, roles, review queue, agreement metrics.

## Conventions
- Small, focused commits with clear messages.
- Never commit datasets, model weights or `.env` files.
