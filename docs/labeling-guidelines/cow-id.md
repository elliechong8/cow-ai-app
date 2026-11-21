# Cow ID labeling guidelines

Draft v0.1.

## Boxes
- One box per visible cow, tight to the body including the head, excluding the tail.
- If more than about 50% of the cow is hidden, label it with the tag `occluded`.
- Don't box cows cut off by the image edge unless most of the body is visible.

## Identity
- Match by ear tag number when it's readable; otherwise by coat pattern.
- Coat patterns: compare the shape of the large black patches on the side, back and head. Check the other side of the cow before deciding, since patterns differ left and right.
- If unsure between two cows, don't guess: mark `uncertain-id` and leave it for review.
- New cow: give the next free tag number and add a note about distinctive markings.

## Categories
Calf, Heifer, Lactating, Dry cow, Bull, Steer.

## Health flags
Healthy, Watch, Needs vet. Always add a note explaining Watch or Needs vet (for example, "limping rear left").
