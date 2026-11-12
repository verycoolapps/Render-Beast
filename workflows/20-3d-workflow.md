# RENDER BEAST — 3D Workflow
# DIMENSION BEAST Step-by-Step Production Pipeline

---

## OVERVIEW

DIMENSION BEAST covers the complete 3D production pipeline — from brief to deliverable. It produces both artistic specifications and technical implementation code. Every deliverable clearly labels what it is: concept spec, runnable code, or rendered visualization.

---

## STEP 1 — BRIEF INTAKE → DIMENSION BEAST

**Reference**: `workflows/17-intake-and-brief.md`

Classify the project:

| Type | Implementation | Deliverable |
|---|---|---|
| Concept specification | No code | Written spec for a 3D artist |
| Blender implementation | Python script | Runnable Blender script |
| Three.js scene | JavaScript | Runnable web component |
| React Three Fiber | JSX | React component |
| Text-to-3D | Prompt | Generation prompt for Meshy/TripoSR/Luma |
| Full pipeline | Multiple | Spec + code + render setup |

Extract at minimum:
- What 3D object/scene is needed
- Intended use (web, game, film, AR, print, visualization)
- Target platform/engine
- Polygon budget (or use case to derive budget)
- Material requirements
- Output format needed

---

## STEP 2 — REFERENCE GATHERING

Identify visual references for the 3D asset:

**Form references**: What does the shape look like from key angles?
**Material references**: What do the surfaces look/feel like?
**Scale references**: How big is it in real-world terms?
**Mood references**: What is the overall aesthetic quality?
**Technical references**: Similar existing 3D work at the target quality level?

If the user has not provided references:
- Derive form from the object's real-world description
- Derive material from the brief's brand positioning
- Derive mood from the concept direction

**Output**: Reference analysis document

---

## STEP 3 — CONCEPT SPECIFICATION

**Reference**: `references/11-3d-production.md` (Geometry and Materials sections)

Develop the full concept specification:

```
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
3D CONCEPT SPECIFICATION
[Asset Name]
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

IDENTITY
Object type:    [What it is]
Scale:          [Real-world dimensions: W × H × D in meters]
Style:          [Photorealistic / Stylized / Low-poly / Technical]
Use case:       [Game / Visualization / Web / AR / Film]

GEOMETRY
Silhouette:     [Description from primary viewing angle]
Primary forms:  [Major volumes]
Secondary forms:[Detail volumes]
Tertiary detail:[Fine surface details]
Topology:       [Clean subdivision / Game-ready / Low-poly]
Polygon budget: [Target triangle count]

MATERIALS
[For each material zone:]
  Name:         [Material name]
  Base color:   [Hex or description]
  Metallic:     [0.0 - 1.0]
  Roughness:    [0.0 - 1.0]
  Surface:      [Smooth / Textured / Procedural]
  Aging:        [New / Used / Worn]
  Special:      [SSS / Transparency / Emissive]

DISTINCTIVE ELEMENT
[What makes this 3D design original — the creative decision that
serves this specific brief rather than generic defaults]
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
```

**Output**: Complete concept specification

---

## STEP 4 — GEOMETRY SPECIFICATION DETAIL

**Reference**: `references/11-3d-production.md` (Part 1)

For each form hierarchy level:

**Primary Forms** (major volumes — the shape in silhouette)
Describe dimensions and proportions precisely. Include: "The main body is a cylinder with height 3× its diameter. The base is a flat disc at 1.5× the cylinder's diameter. The top tapers to 70% of the main body's diameter."

**Secondary Forms** (articulation details)
"Horizontal groove lines at 1/3 and 2/3 height. Slight 5° inward taper from base to top. The grip section between grooves is knurled with diamond pattern."

**Tertiary Details** (fine surface details)
"Small manufacturer's mark embossed on the base. Chamfered edges at all transitions. Surface shows very slight machining marks on flat faces."

**Anti-slop check**:
- Does the design have a distinctive silhouette?
- Is every detail present for a reason (functional, brand, narrative)?
- Does it avoid generic 3D defaults (perfect cubes, uniform spheres, generic sci-fi forms)?

**Output**: Detailed geometry specification

---

## STEP 5 — MATERIAL SPECIFICATION

**Reference**: `references/11-3d-production.md` (Part 2 — PBR Workflow)

For every material in the asset:

```
MATERIAL SPECIFICATION
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
Material:       [Name]
Type:           [Metal / Dielectric / Transparent / SSS / Emissive]
Base Color:     #[HEX]
Metallic:       [0.0 - 1.0]
Roughness:      [0.0 - 1.0]  
Specular:       [0.5 default for dielectrics]
Normal Strength:[1.0 default]
Surface Detail: [Procedural: pattern type | Texture: description]
Aging Detail:   [Scratches direction + density | Fingerprints | Wear pattern]
Special Props:  [SSS scatter radius + color | Transmission IOR | Emissive power]
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
```

**Output**: Complete material specification for all materials

---

## STEP 6 — LIGHTING DESIGN

**Reference**: `references/11-3d-production.md` (Part 3)

Design the lighting environment:

```
LIGHTING DESIGN
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
Setup Type:     [Three-point studio / HDRI environment / 
                 Motivated (practical sources) / Cinematic]

HDRI (if used): [Description of environment image — outdoor noon /
                 studio softbox array / twilight outdoor / etc.]

Key Light:
  Type:         [Area / Sun / Spot]
  Position:     [Degrees from front, degrees from horizontal]
  Color Temp:   [Kelvin value]
  Intensity:    [Relative value]
  Size:         [Softness — small=hard, large=soft]
  
Fill Light:
  Ratio:        [1:3 relative to key — lower ratio=lower contrast]
  Position:     [Opposite side from key]
  
Rim Light:
  Present:      [Y/N]
  Strength:     [Relative to key]
  
Background:
  Type:         [Solid color / Gradient / HDRI / Infinite floor]
  Color:        [If solid or gradient — specify]

Shadow:
  Type:         [Sharp / Soft / No shadow]
  Contact shadows: [Y/N]
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
```

**Output**: Complete lighting design specification

---

## STEP 7 — TECHNICAL SPECIFICATION

**Reference**: `references/11-3d-production.md` (Part 4), `references/15-technical-standards.md` (3D TECHNICAL)

```
TECHNICAL SPECIFICATION
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
Target Software:  [Blender 4.x / Three.js / Unity / Unreal]
Export Format:    [GLTF/GLB / FBX / OBJ / USDZ]
Scale:            [Meters — X W × Y H × Z D]
Units:            [Meters]
Origin/Pivot:     [Center of base / Center of mass / World origin]
Coordinate:       [Y-up for Three.js; Z-up for Blender native]
UV Layout:        [Required Y/N — if Y, single UV set or multiple?]
Texture Atlas:    [Y/N — combined into one texture sheet?]
Texture Res:      [512 / 1024 / 2048 / 4096 px]
LOD Required:     [Y/N — if Y, LOD chain: LOD0/1/2/3 targets]
Rigging:          [Y/N — if Y, describe rig requirements]
Animations:       [Y/N — if Y, list animation clips needed]
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
```

**Output**: Complete technical specification

---

## STEP 8 — TOOL SELECTION

Based on project requirements, select the implementation approach:

| Approach | Use When | RENDER BEAST Provides |
|---|---|---|
| **Blender Python** | Full 3D pipeline, offline rendering | Python script |
| **Three.js** | Web display, interactive | JavaScript module |
| **React Three Fiber** | React-based web app | React component + JSX |
| **Text-to-3D prompt** | Quick geometry starting point | Optimized prompt |
| **Manual spec** | For 3D artist to implement | Complete written spec |

For complex projects, provide multiple paths:
- Code implementation for web display
- Specification for 3D artist refinement
- Text-to-3D prompt for starting point geometry

**Output**: Tool selection decision with rationale

---

## STEP 9 — BLENDER PYTHON SCRIPT (if applicable)

**Reference**: `references/11-3d-production.md` (Part 5)

Provide a complete, executable Blender Python script. The script must:
- Clear any existing scene content
- Create the specified geometry (or placeholder if complex)
- Create all PBR materials with specified values
- Set up the lighting design
- Configure the camera with correct focal length and position
- Configure render settings (Cycles, samples, resolution)
- Include clear comments explaining each section
- Include export function for the target format

```python
"""
RENDER BEAST — [Asset Name] Blender Scene
Generated for: [Project Name]
Blender 4.x compatible
"""
import bpy
import mathutils

# [Complete implementation from references/11-3d-production.md templates]
# Customized to this specific asset's specifications
```

**Output**: Complete Blender Python script with all specified geometry, materials, lighting, and render setup

---

## STEP 10 — THREE.JS COMPONENT (if applicable)

**Reference**: `references/11-3d-production.md` (Part 6)

Provide a complete Three.js implementation:
- WebGL renderer with correct tone mapping
- Three-point lighting + environment
- PBR materials matching specification
- Camera matching specification
- OrbitControls for interaction
- Responsive canvas
- Performance considerations (shadow map size, pixel ratio cap)
- GLTFLoader integration if model file is external

```javascript
// RENDER BEAST — [Asset Name] Three.js Implementation
// [Complete implementation from references/11-3d-production.md templates]
// Customized to this specific asset's specifications
```

**Output**: Complete Three.js module

---

## STEP 11 — REACT THREE FIBER COMPONENT (if applicable)

**Reference**: `references/11-3d-production.md` (Part 7)

Provide a complete R3F component:
- Canvas with correct renderer settings
- Environment + lighting setup
- Material configuration matching PBR spec
- Suspense boundary with fallback
- OrbitControls
- Responsive and accessible
- Proper cleanup/dispose pattern

```jsx
// RENDER BEAST — [Asset Name] React Three Fiber Component
// [Complete implementation from references/11-3d-production.md templates]
// Customized to this specific asset's specifications
```

**Output**: Complete React component file(s)

---

## STEP 12 — TEXT-TO-3D PROMPT (if applicable)

**Reference**: `references/14-prompt-engineering.md` (Part 9)

Provide optimized prompts for text-to-3D generators:

**For Meshy / TripoSR / Luma Genie**:
```
TEXT-TO-3D PROMPT
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
Target Generator: [Meshy / TripoSR / Luma Genie]

Prompt:
[Object type] [specific form description] [material description]
[style: realistic/stylized] [quality level]

Additional notes:
[Any image reference to upload alongside the text prompt]
[Expected quality level and what may need adjustment]
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
```

**Output**: Text-to-3D generation prompt with guidance

---

## STEP 13 — RENDER SETUP

**Reference**: `references/11-3d-production.md` (Part 5 — Rendering)

```
RENDER SETUP
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
Engine:         [Cycles / EEVEE / Three.js WebGL]
Resolution:     [2048 × 2048 / 4096 × 4096 / custom]
Samples:        [512 / 1024 / 4096 — higher = quality, slower]
Denoising:      [Y — OpenImageDenoise recommended]
Device:         [GPU preferred; CPU fallback]
Camera:
  Position:     [X, Y, Z coordinates]
  Target:       [What the camera points at]
  Focal Length: [mm — 85mm for products, 50mm for environments]
  Aperture:     [f/8 for sharp, f/2.8 for shallow DOF effect]
Color Mgmt:     [Filmic / ACES / Standard]
Output:
  Format:       [PNG-RGBA / EXR / JPEG]
  Color Depth:  [16-bit for PNG, 32-bit for EXR]
  Naming:       [render_[asset]_[angle]_[variant]]
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
```

**Output**: Complete render configuration

---

## STEP 14 — OUTPUT INSPECTION

Inspect any generated or rendered output:
- Does the geometry match the specification?
- Are materials correctly applied and behaving physically?
- Is lighting producing the intended mood and revealing form correctly?
- Are there topology errors (z-fighting, inverted normals, artifacts)?
- Technical quality (resolution, denoising, clean edges)?

**Anti-slop check** (`references/13-anti-slop-quality-gates.md` — 3D section):
- Generic marble floor with studio lighting?
- Random floating particle system?
- Over-smooth, uniform plastic material on everything?
- Generic sci-fi environment (dark + neon)?

**Decision**: Accept / Fix / Regenerate

---

## STEP 15 — ANTI-SLOP GATE

Apply 3D-specific slop detection and run quality tests:
- Originality test: Does this asset have design decisions specific to this brief?
- Intentionality test: Does every detail serve a purpose?
- Material test: Does each material communicate the right quality?
- Lighting test: Does the lighting reveal form and create mood?

**Output**: Anti-slop report

---

## STEP 16 — QUALITY SCORING

**Reference**: `evals/22-quality-evaluation.md`

Score the 3D deliverable with 3D-specific evaluation criteria:
- For specification: Score based on completeness and creative quality
- For rendered visualization: Score the actual rendered image
- For code: Score implementation quality + visual result

---

## STEP 17 — EXPORT PIPELINE

```
EXPORT PIPELINE
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
Pre-export checklist:
[ ] All transforms applied (Apply All in Blender)
[ ] Scale is correct in real-world units
[ ] Origin/pivot set correctly
[ ] UV maps are within 0-1 space, no overlaps
[ ] Materials named descriptively
[ ] Mesh named descriptively
[ ] Animation baked if required

Export settings:
Format:         [GLB / FBX / OBJ]
Scale:          [1.0 — do not rescale on export]
Include:
  Geometry:     [Y]
  Materials:    [Y]
  Textures:     [Embedded in GLB / Separate folder]
  Animation:    [Y/N]
  
Post-export validation:
[ ] File opens correctly in target application
[ ] Materials display correctly
[ ] Scale is correct
[ ] Animations play correctly (if applicable)
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
```

---

## STEP 18 — FINAL DELIVERY PACKAGE

```
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
DIMENSION BEAST — FINAL DELIVERY
[Asset Name]
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

WHAT IS DELIVERED IN THIS PACKAGE:
[ ] Concept Specification (written)
[ ] Geometry Specification (detailed)
[ ] Material Specification (PBR values)
[ ] Lighting Design (setup document)
[ ] Technical Specification (formats, scale, UV)
[ ] Blender Python Script (runnable)
[ ] Three.js Implementation (runnable)
[ ] React Three Fiber Component (runnable)
[ ] Text-to-3D Prompt (for Meshy/TripoSR)
[ ] Render Setup (configuration)
[ ] Export Pipeline (checklist + settings)

WHAT IS NOT DELIVERED:
(A downloadable 3D file cannot be created by RENDER BEAST alone — 
 the scripts above must be run in Blender/browser to produce the actual asset)

CREATIVE CONCEPT: [Brief description]
DISTINCTIVE DESIGN DECISION: [What makes this original]

TECHNICAL SUMMARY:
Polygon Budget: [X] triangles
Texture Resolution: [X]px
Export Format: [X]
Target Platform: [X]

QUALITY SCORE: [X]/100 — [LEVEL]
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
```
