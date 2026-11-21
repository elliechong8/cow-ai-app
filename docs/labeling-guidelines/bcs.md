# Body condition score (BCS) labeling guidelines

Draft v0.1. Have a vet or experienced dairy nutritionist review before using for real training data.

## What BCS is
A 1–5 score of a dairy cow's body fat reserves, judged from the rear and side over the pelvis and loin. Labeled in **0.25 steps** (2.75, 3.00, 3.25…). Most healthy dairy cows score between about 2.5 and 4.0, and the ideal range depends on lactation stage.

## Image requirements
- View: from above or rear-oblique, with the hooks, pins and tailhead visible
- Cow standing, not mid-step
- Skip and flag images that are blurry, too dark, or where the pelvis area is blocked

Flag reasons: `blurry`, `occluded`, `wrong-angle`, `not-standing`, `multiple-cows`.

## Anatomy points (optional keypoints)
| Point | Where |
|---|---|
| Hooks (L and R) | Front points of the pelvis, at the top of the hip |
| Pins (L and R) | Rear points of the pelvis, either side of the tail |
| Tailhead | Where the tail joins the body |
| Thurl | Midway between hook and pin on the side |
| Short ribs | Ends of the loin vertebrae, in front of the hooks |

## Scoring guide
| Score | Look |
|---|---|
| **1.0–1.75** (very thin) | Bones sharp and clearly visible; deep cavity around tailhead; short ribs very prominent |
| **2.0–2.75** (thin) | Hooks and pins angular; short ribs visible; tailhead area hollow |
| **3.0–3.25** (moderate) | Hooks and pins rounded but visible; slight padding around tailhead; smooth loin |
| **3.5–3.75** (good / fleshy) | Hooks and pins rounded and padded; tailhead area filled; short ribs hard to see |
| **4.0–5.0** (fat) | Bones barely or not visible; fat folds around tailhead and pins; back looks flat |

Tip: decide the band first (thin / moderate / fat), then refine to the quarter point.

## Edge cases
- **Can't decide between two scores:** pick the lower one and add the tag `borderline`.
- **Hair coat or dirt hides the shape:** flag `occluded`, don't guess.
- **Recently calved cows** often look thinner; score what you see, not what you expect.

## QA targets (see `../qa-process.md`)
- Two labelers agree within ±0.25 on at least 85–90% of images
- Disagreements over 0.5 go to a reviewer
