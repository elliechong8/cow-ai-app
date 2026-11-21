# ML (planned)

| Folder | Task | Starting data | Approach |
|---|---|---|---|
| `detection/` | Find every cow in an image | Roboflow cattle datasets, OpenCows2020 detection split | Fine-tune Ultralytics YOLO |
| `reid/` | Recognise individual cows | OpenCows2020 identity split, Cows2021 | Metric learning (embeddings + nearest neighbour) |
| `bcs/` | Predict body condition score | BCS Database (Catania), Dryad RGB+depth BCS | Keypoints + regression / classification |

Each folder will hold a `train.py`, an `eval.py`, a short README with results, and an export step that the web app can call for suggestions.

Model weights (`*.pt`, `*.onnx`) and `runs/` are gitignored. Store weights in a release or cloud bucket.
