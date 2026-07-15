# Wind Spirit one-wing identity contract

## Fixed silhouette rule

- Keep exactly one three-feather wing in every frame: the wing on the image/viewer left.
- Remove the complete wing on the image/viewer right, including every feather tip and the shoulder attachment. Reconstruct a clean hood/body outline and background where it was removed.
- `image left` and `image right` are screen coordinates. The remaining wing stays on image left even when the pet moves or looks in another direction.
- Never duplicate, mirror, center, move, or replace the remaining left wing.

## No-hand rule

- Wind Spirit has no arms and no hands.
- Do not add arms, hands, sleeves, paws, fingers, hand-like shapes, or handheld props.
- The `waving` greeting is expressed only by the single image-left wing flapping through a clear raise-and-return cycle.

## Other identity locks

- Preserve the existing single two-leaf head tuft on image right in front-facing poses; never add a second tuft.
- Preserve the black visor, two white eyes, teal chest emblem, layered cape, two teal feet, palette, proportions, scale, baseline, and 2D sprite style.
- No text, logo, yellow markup box, guide marks, detached effects, shadows, glows, scenery, or chroma-key colors inside the pet.
