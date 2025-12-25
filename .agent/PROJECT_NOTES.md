# Project Notes - Inculc8

## 3D Model Configuration

### miles2.glb Model Bone Setup
⚠️ **IMPORTANT**: This model has a non-standard bone rotation setup!

**Rotation Axis Mapping:**
- `rotation.x` = **Horizontal turning** (yaw) - controlled by mouse.x
- `rotation.z` = **Vertical nodding** (pitch) - controlled by mouse.y
- `rotation.y` = **Roll/tilt** - NOT USED (causes unwanted tilting)

**Mouse to Rotation Mapping:**
```javascript
// Correct mapping for this model:
const targetYaw = mouse.x * 0.65;   // mouse.x → controls rotation.x (horizontal turn)
const targetPitch = mouse.y * 0.65; // mouse.y → controls rotation.z (vertical nod)

// Apply to bones:
headPitch(rotation.x) ← gets targetYaw (from mouse.x)
headYaw(rotation.z) ← gets targetPitch (from mouse.y)
```

This is unconventional but required for this specific model's rig.

## Development

**Run command:**
```bash
nvm use 20.9.0 && npm run dev
```

**Tech stack:**
- Astro 5.16.6
- Three.js 0.182.0
- GSAP 3.14.2 (with quickTo for smooth mouse tracking)
- TypeScript
