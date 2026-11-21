# API (planned)

Backend for shared, multi-user labeling.

## Planned data model
- `farms`: a farm / herd owner
- `cows`: tag, RFID, name, breed, category, sex, birth date, sire, dam, health status
- `images`: file path in storage, source dataset, capture date, camera
- `annotations`: image, cow, bbox, keypoints, BCS, labeler, created_at
- `reviews`: annotation, reviewer, status (approved / rejected / needs fix), comment
- `users`: role (labeler / reviewer / admin)

## Planned endpoints
- `POST /images`, `GET /images?unlabeled=true`
- `POST /annotations`, `PATCH /annotations/:id`
- `GET /review-queue` (sampled), `POST /reviews`
- `GET /metrics/agreement`
- `GET /export?format=coco|yolo|csv`

## Options
- **Supabase:** Postgres, auth and storage in one; fastest to ship
- **FastAPI + Postgres + S3:** more backend practice
