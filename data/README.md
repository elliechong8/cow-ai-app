# Open cow datasets

Download datasets into `data/raw/<dataset-name>/`. That folder is ignored by git (see `.gitignore`), so datasets are never pushed to GitHub. Conversion scripts live in `data/scripts/`.

**Always check each dataset's license before using it,** especially for anything commercial. Cite the paper when a dataset asks you to.

## Start here (easiest)

| Dataset | What it has | Size | Good for |
|---|---|---|---|
| [Roboflow Universe – cattle detection](https://universe.roboflow.com/search?q=cattle) | Many small cow/cattle box datasets, exportable as COCO JSON or YOLO | ~100s–1,000s images each | Testing import, detection boxes |
| [OpenCows2020](https://data.bris.ac.uk/data/dataset/10m32xl88x2b61zlkkgz3fml17) (Univ. of Bristol) | Holstein-Friesian images: detection boxes + individual identity crops | 2.1 GB zip | Cow ID / re-identification |

## Individual identification (re-ID)

- **Cows2021** (Univ. of Bristol): top-down in-barn images of Holsteins with boxes and identity labels, plus videos. Paper: https://arxiv.org/abs/2105.01938
- **MultiCamCows2024** (Univ. of Bristol): ~100k images of 90 cows from 3 barn cameras. Paper: https://arxiv.org/abs/2410.12695
- **CoBRA re-identification youngstock** (KU Leuven / Ghent): Holstein segments sorted by identity and behaviour. https://zenodo.org/records/15018518

## Body condition score (BCS)

- **BCS Database** (Univ. of Catania / Penn Vet): 207 images of 29 cows, labeled anatomical points and BCS. https://iplab.dmi.unict.it/BCS/
- **Labeled RGB + depth images for BCS** (Dryad): Criollo cows, depth/grayscale/edge images. Start with the ~180 MB processed zip, not the 34 GB raw files. https://datadryad.org/dataset/doi:10.5061/dryad.tqjq2bw4s

## Suggested folder layout

```
data/
  raw/
    roboflow-cattle/    # COCO or YOLO export
    opencows2020/
    bcs-catania/
  processed/            # converted files ready to import
  scripts/
```
