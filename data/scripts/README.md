# Data scripts (planned)

- `coco_to_cowai.py`: convert a COCO JSON export (e.g. from Roboflow) into the web app's import format
- `yolo_to_cowai.py`: same for YOLO `.txt` labels + `data.yaml`
- `cowai_to_coco.py`: export approved labels back to COCO for training

Put downloaded datasets in `data/raw/<dataset-name>/`. That folder is gitignored.
