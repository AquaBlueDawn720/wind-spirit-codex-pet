# Wind Spirit look mechanics

## Identity lock

- Keep the rounded white hood, black visor face, two simple white eyes, teal chest emblem, layered cape skirt, and small teal feet unchanged.
- Keep exactly one attached three-feather wing on the image/viewer left in every pose. The image-right wing is absent and must never reappear, regardless of gaze direction.
- Wind Spirit has no arms or hands. Never add a hand-like gesture, sleeve, paw, finger, or handheld prop.
- The only head tuft is the two-leaf cluster attached to the character's anatomical left side. It is intentionally asymmetric. Never duplicate, center, mirror, or move it to anatomical right.
- As the head turns, the tuft may bend, lag, or become partly occluded, but it must remain attached to anatomical left in every direction.
- The lower torso, feet, and cape baseline are the stable anchor. Preserve scale and registration.

## Natural gaze mechanism

- The white eyes are flat features on a black visor, not physical eyeballs. Move and slightly reshape both white eye marks together within the visor while keeping them simple and inside the face aperture.
- Eyes lead each direction. The hood then makes a small natural pitch or yaw, followed by gentle motion in the single tuft and the single image-left wing.
- The tuft follows with a soft wind-swept lag. The single image-left wing may pitch subtly toward the target but stays on image left; the cape stays mostly stable.
- Do not rotate, skew, or tilt the whole sprite. Do not add pupils, replacement eyes, arrows, labels, effects, or props.

## Cardinal pose families

- `000 up`: eyes move clearly to the top of the visor; hood pitches slightly upward; tuft lifts; the single image-left wing rises a little. Feet and cape baseline stay anchored.
- `090 screen-right`: eyes move clearly toward screen-right; hood yaws slightly toward screen-right. The character-left tuft remains on its anatomical side and reads as the leading/near-side tuft without being centered.
- `180 down`: eyes move clearly to the bottom of the visor; hood nods down; tuft and the single image-left wing settle slightly downward. Keep the full face readable.
- `270 screen-left`: eyes move clearly toward screen-left; hood yaws slightly toward screen-left. The character-left tuft becomes the far-side feature and may be partially occluded behind the hood, but it must not flip to anatomical right.

## Motion budget and continuity

- Use sixteen evenly spaced clockwise gaze poses. Each 22.5-degree step changes eye position, hood angle, tuft bend, and wing pitch by a small comparable amount.
- Keep the same body height, lower-body anchor, face aperture, palette, and chest-emblem position across the loop.
- Preserve continuity across `157.5 -> 180` and `337.5 -> 000`; no jumps, flips, scale pops, or sudden changes in tuft visibility.
