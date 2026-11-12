# RENDER BEAST — Prompt Engineering
# Advanced Prompt Construction for All Four Engines

---

## THE RENDER BEAST PROMPT PHILOSOPHY

A prompt is not a wish. It is a specification.

The difference between "a beautiful portrait" and a prompt that reliably produces a beautiful portrait is the difference between hope and engineering. RENDER BEAST treats prompt construction as a technical discipline with learnable patterns, testable structures, and iterative improvement loops.

The goal is not to find magic keywords. The goal is to communicate precisely what should appear, in what configuration, with what quality — so that the generation system has the information it needs to succeed.

---

## PART 1 — CONTEXT ENGINEERING

Before writing a single descriptive word, establish the context frame.

### The Context Hierarchy

**Level 1 — Intent Declaration**
State what this is and why it matters.
Not: "A photo of a coffee cup"
Better: "A product photography shot for a premium artisanal coffee brand"

**Level 2 — Style Anchor**
Establish the visual language before describing the subject.
Not: "A photo of a coffee cup in a café"
Better: "Editorial food photography in the style of Bon Appétit magazine — warm, intimate, shallow depth of field, natural window light"

**Level 3 — Subject Specification**
Now describe the specific subject within that established context.
"A ceramic matte-black coffee cup, slightly imperfect handmade quality, steam rising, sitting on a wooden surface with morning light from the left"

**Level 4 — Compositional Precision**
Specify the frame structure.
"Close-up shot, subject positioned left of center, right third occupied by softly blurred background, slight bokeh from 85mm equivalent focal length"

**Level 5 — Quality Anchors**
Reinforce the standard without generic fluff.
"Sharp focus on ceramic texture, natural color grade, no post-processing look"

---

## PART 2 — SUBJECT DEFINITION

### Primary Subject
Describe with maximum specificity:
- **What it is** (noun)
- **Its specific state** (verb/adjective)
- **Its defining characteristics** (the details that matter)
- **Its relationship to environment** (how it exists in the space)

**Weak**: "A warrior"
**Strong**: "A warrior woman in her 30s, leather and bronze armor worn and battle-scratched, long dark hair loose and windswept, standing at the edge of a cliff at dusk, sword lowered at her side"

### Secondary Subjects
Elements that support but do not compete with the primary:
- Their relationship to the primary (behind, to the side, below)
- Their relative size and visual weight
- Their contribution to the narrative

### Environmental Subjects
The world the primary subject inhabits:
- Specific location type (not "a forest" — what kind of forest, what season, what time)
- Environmental state (weather, lighting conditions, activity level)
- Scale indicators (what tells you how large or small the space is)

---

## PART 3 — COMPOSITION CONTROL LANGUAGE

These specific terms produce consistent compositional results across most generators:

**Framing**
- "Subject in the left/right/center of the frame"
- "Subject occupying [X]% of the frame"
- "Extreme close-up / close-up / medium shot / wide shot / bird's eye view"
- "Looking directly at camera / at 3/4 angle / in profile / from behind"
- "Portrait orientation / landscape orientation"

**Depth**
- "Shallow depth of field, background blurred"
- "Deep focus, everything sharp"
- "Foreground element slightly blurred, subject sharp"
- "Rack focus effect — foreground sharp, subject soft" (note: some generators handle this)

**Space**
- "Generous negative space [direction]"
- "Tight composition, subject fills the frame"
- "Rule of thirds — subject at left/right intersection"
- "Centered, symmetrical composition"
- "Dynamic diagonal composition"

**Perspective**
- "Eye level"
- "Looking up at / low angle camera"
- "Looking down at / high angle camera"
- "Extreme low angle — worm's eye"
- "Overhead / bird's eye / flat lay"
- "Dutch angle / canted frame"

---

## PART 4 — LIGHTING CONTROL VOCABULARY

**Direction**
- "Front lit / two-dimensional light" (flatter)
- "45-degree side lighting from [left/right]"
- "90-degree side lighting — split lighting"
- "Back lit / rim lighting only"
- "Top down / overhead lighting"
- "Under lit / light from below" (use intentionally)

**Quality**
- "Soft diffused light / large soft source" (soft shadows)
- "Hard directional light / small source" (sharp shadows)
- "Studio softbox lighting" (product photography standard)
- "Natural window light, diffused"
- "Open shade / overcast diffuse light"

**Color Temperature**
- "Warm golden light [3000K]"
- "Neutral daylight [5500K]"
- "Cool blue light [7000K+]"
- "Golden hour / magic hour light"
- "Blue hour / twilight light"
- "Mixed lighting: warm interior, cool exterior"

**Specific Sources**
- "Sunlight from camera left, casting defined shadows"
- "Single practical lamp, intimate pool of warm light"
- "Moonlight, cool and directional"
- "Candle light, flickering warm, low contrast"
- "Neon sign reflecting on wet pavement" (must be motivated)
- "LED ring light, clinical and direct"

---

## PART 5 — STYLE CONSISTENCY TECHNIQUES

### Style Anchor Method
Begin with a clear style statement that sets the frame for all other descriptors:
- "Editorial photography" → viewers (and generators) expect certain light, composition, model direction
- "Concept art by [direction, not name]" → expects painterly rendering, strong silhouette, atmospheric
- "Product photography" → expects clean background, accurate color, sharp materials

### Aesthetic Vocabulary
Terms that communicate consistent visual qualities:

**For photography**: photorealistic, editorial, documentary, commercial, vernacular, snapshot aesthetic, medium format, large format, 35mm film, analog, digital clean

**For illustration**: painterly, digital painting, ink and watercolor, vector, flat design, isometric, woodcut, lithograph, risograph, screen print

**For 3D**: photorealistic rendering, stylized, low poly, PBR render, clay render (no texture), wireframe, NPR (non-photorealistic)

**For mood**: melancholic, euphoric, nostalgic, clinical, intimate, expansive, claustrophobic, serene, tense, dreamlike, grounded

---

## PART 6 — MATERIAL CONTROL VOCABULARY

**Metal**
- "Polished stainless steel, mirror-like reflections"
- "Brushed aluminum, directional grain, matte metallic"
- "Raw iron, rough surface, slight oxidation"
- "Gold, 18K, warm reflection, slight warmth in highlights"
- "Aged copper, patina, blue-green oxidation on surface"

**Fabric**
- "Heavyweight cotton, rough weave, matte surface"
- "Silk, fluid, high-sheen, soft reflections"
- "Wool, textured, warm, light catches fiber tips"
- "Denim, broken in, faded, fiber detail visible"
- "Leather, natural grain, slight sheen, aged"

**Stone**
- "Rough concrete, aggregate visible, matte gray"
- "Polished marble, veining pattern, cool reflection"
- "Natural sandstone, warm tone, granular surface"
- "Black granite, specular reflection, cool tone"

**Glass**
- "Clear borosilicate glass, slight distortion, clean"
- "Frosted glass, diffused transmission, matte surface"
- "Colored glass, light transmission tinted [color]"
- "Cracked/broken glass, refraction at edges"

**Organic**
- "Smooth skin, slight subsurface scattering, natural pores"
- "Wood grain, natural variation, warm tone, ring patterns"
- "Plant material, waxy leaf surface, light transmission at edges"
- "Stone, rough, matte, variation in surface color"

---

## PART 7 — MODEL-SPECIFIC ADAPTATION

### Midjourney

**Prompt structure**: Subject + environment + style + technical parameters
**Parameters**: `--ar [ratio]` `--v 6.1` `--style raw` (for more literal) `--stylize [0-1000]` (default 100)
**Strengths**: Aesthetic quality, composition, lighting
**Weaknesses**: Exact text, hands, complex compositions with many elements
**Negative prompt**: `--no [unwanted elements]`

```
Example Midjourney prompt:
editorial product photography, matte black ceramic coffee mug, single white daisy resting against it, morning window light from left, soft shadows, shallow depth of field, warm neutral background --ar 4:5 --style raw --v 6.1 --no text, watermark, logo, digital artifacts
```

### DALL-E 3 (ChatGPT/API)

**Prompt structure**: Natural language, descriptive sentences
**Parameters**: Size, quality, style options in API
**Strengths**: Following complex instructions, combining concepts, text rendering (improved)
**Weaknesses**: Sometimes overly literal, compositional variety limited
**Note**: Does not support negative prompts — rephrase as positive exclusions ("ensure the background is minimal")

```
Example DALL-E 3 prompt:
A product photography image of a handmade ceramic matte-black coffee mug. The mug sits on a weathered light wood surface. Single white flower leans against the mug. Light enters from a window to the left, creating soft warm shadows. The background is a blurred warm neutral wall. No text, no logos, no watermarks. Editorial photography quality. 4:5 portrait format.
```

### Stable Diffusion / AUTOMATIC1111

**Prompt structure**: Comma-separated tags and phrases, (parentheses for increased weight), [brackets for decreased weight]
**Strengths**: Highly customizable via LoRAs and controlnet, style consistency possible, local generation
**Weaknesses**: Requires model selection knowledge, inconsistent without tuning
**Negative prompt**: Explicit comma-separated exclusion list

```
Example SD prompt:
editorial product photography, ceramic coffee mug, matte black surface, (white flower:1.2), window light, soft shadows, shallow depth of field, warm tones, (bokeh:0.8), film grain, natural, authentic

Negative: watermark, text, logo, digital artifacts, oversaturated, plastic looking, (neon:1.5), (glowing:1.4), blurry subject, bad composition
```

### Flux (via Fal.ai, Replicate, etc.)

**Prompt structure**: Similar to natural language but responds well to detailed description
**Parameters**: Model variant (Flux.1 Pro, Dev, Schnell), guidance scale, steps
**Strengths**: Photorealism, lighting quality, detail fidelity, text rendering (best-in-class)
**Weaknesses**: Requires longer descriptive prompts for best results

```
Example Flux prompt:
Photorealistic editorial photograph of a handmade matte black ceramic coffee mug on a worn wooden surface. A single white chamomile flower rests against the mug. Morning light streams softly from a window on the left, casting gentle warm shadows. Background is a softly blurred warm white wall. The image has natural film-like quality, shallow depth of field, 85mm lens equivalent, warm tonal quality. High resolution, sharp focus on mug texture.
```

---

## PART 8 — VIDEO PROMPT PATTERNS

### Runway Gen-4 / Pika / Kling

**Single shot prompt structure**:
`[Subject + action] [camera framing] [camera movement] [environment] [lighting] [style]`

```
Example Runway prompt:
Close-up shot of a runner's face, eyes forward, slight exertion visible. Camera stays steady with subtle handheld breathing movement. Golden hour warm light from camera left, rim light separating face from blurred trail background. Cinematic, shallow depth of field, photorealistic.
```

**Motion language that works**:
- "Slow push in toward [subject]"
- "Camera pulls back slowly revealing [environment]"
- "Smooth handheld follow shot"
- "Static camera, [subject] moves through frame"
- "Slow pan from [point A] to [point B]"

**Motion language that often fails**:
- Complex camera paths (dolly + pan + tilt simultaneously)
- Very fast movements
- Precise camera positioning changes within one clip

### Sora

**Strength**: Complex scenes, multi-element movement, temporal consistency
**Prompt approach**: Describe the entire shot as a filmmaker would to their DP
- Include specific camera language
- Describe all elements including background movement
- Specify lighting conditions precisely

---

## PART 9 — 3D PROMPT PATTERNS

### Text-to-3D (Meshy, TripoSR, Luma Genie)

**What works**:
- Simple to medium complexity objects
- Clear primary geometry
- Specific material descriptions

**What struggles**:
- Complex organic forms with fine detail
- Transparent materials
- Extreme detail requirements
- Multi-part assemblies

```
Example Meshy prompt:
Futuristic gaming headset, over-ear design, matte black hard plastic shell, metallic accent rings on earcups, fabric mesh cushions, rigid headband with minimal padding, clean geometric design language, professional product visualization style
```

**For best results with text-to-3D**:
1. Provide a reference image alongside the text prompt
2. Keep geometry simple enough that the topology will be usable
3. Plan for PBR material assignment in the 3D tool after generation
4. Expect to retopologize for game/interactive use

---

## PART 10 — NEGATIVE CONSTRAINT ENGINEERING

### Why Negative Prompts Matter

Positive prompts tell the generator what to create. Negative prompts prevent the generator's default tendencies from corrupting the output.

Every model has biases — compositional defaults, style tendencies, detail additions that it defaults to without being asked. Negative prompts counteract these.

### Negative Prompt Architecture

**Layer 1 — Universal Exclusions** (always include)
```
watermark, signature, text overlay, logo, blurry, low quality, low resolution, compression artifacts, overexposed, underexposed
```

**Layer 2 — Anti-Slop Exclusions** (almost always include)
```
generic ai aesthetic, stock photo composition, oversaturated, plastic looking, artificial, neon glow, random geometric shapes, purple-blue gradient, glassmorphism
```

**Layer 3 — Style-Specific Exclusions** (based on direction)
```
(Photorealism): painting, illustration, cartoon, anime, 3d render
(Illustration): photography, photorealistic, CGI
(Minimalist): busy, cluttered, complex, detailed, ornate
(Product): people, hands, text, logos, distracting background elements
```

**Layer 4 — Technical Exclusions** (based on common generator artifacts)
```
bad anatomy, deformed hands, extra fingers, mutation, duplicate, broken, malformed, bad proportions
```

### Stable Diffusion Negative Weight Syntax
In AUTOMATIC1111 and compatible interfaces:
- `(item:1.5)` — increase weight by 50%
- `[item:0.5]` — decrease weight by 50%
- `((item))` — standard double emphasis
- `(neon glow:1.8), (purple gradient:1.9)` — strong exclusion of slop patterns

---

## PART 11 — PROMPT DEBUGGING

When output does not match intent, diagnose systematically:

### Problem: Wrong style
**Check**: Is the style anchor strong enough? Is it at the beginning of the prompt?
**Fix**: Make the style declaration more specific. Add photographer/artist direction (describe the style, not the name).

### Problem: Wrong composition
**Check**: Are compositional instructions specific? Camera angle/distance/framing clearly stated?
**Fix**: Add explicit composition language. Reduce subject description length (long descriptions make composition instructions lose priority).

### Problem: Wrong lighting
**Check**: Is lighting described in terms of source and direction, not just mood?
**Fix**: "Soft window light from the left" rather than "beautiful natural lighting."

### Problem: Wrong materials
**Check**: Are materials described with PBR properties (rough/smooth, matte/glossy)?
**Fix**: Add specific material properties: "matte concrete surface with rough aggregate texture" rather than "concrete."

### Problem: Slop patterns appearing despite negative prompt
**Check**: Are slop pattern exclusions in the negative prompt? Strong enough weight?
**Fix**: Increase weight of exclusions. Add more specific pattern names. Rephrase as positive direction ("warm wood background" rather than "no gradient background").

### Problem: Text is garbled
**Fix**: Use post-production typography strategy. Remove text from the generation prompt. Add text in design software after generation.

### Problem: Inconsistency between generations
**Fix**: Use a seed value (available in most generators). Reference a successful generation and make incremental changes.
