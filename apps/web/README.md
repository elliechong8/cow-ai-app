# Web app: labeling UI

Single-file prototype (`index.html`). Open it in a browser, or run `python3 -m http.server 8000` in this folder.

## Features
- Upload or drag-and-drop photos; draw bounding boxes
- Cow profiles: tag, name, breed, category, sex, health, notes
- Re-ID suggestions from a simple coat-pattern + colour signature (not ML yet)
- Herd view with filters, search, sighting history
- Export: annotations JSON and herd CSV
- Undo, Delete, Esc, Ctrl/Cmd+Z

## Next
- Body condition score labeling (see `docs/labeling-guidelines/bcs.md`)
- Import COCO / YOLO annotations
- Migrate to React + TypeScript + Vite
