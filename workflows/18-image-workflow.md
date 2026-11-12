# RENDER BEAST — Image Workflow
# IMAGE BEAST Step-by-Step Production Pipeline

---

## OVERVIEW

This workflow transforms any image request into a production-ready creative package. Follow each step in sequence. Quality gates prevent weak output from advancing.

---

## STEP 1 — BRIEF INTAKE → IMAGE BEAST

**Input**: User's image request (any form — simple or detailed)
**Reference**: `workflows/17-intake-and-brief.md`

Classify the request:
- **Quick request** ("make an image of X") → Quick Brief, proceed directly
- **Specific brief** (style, context, platform specified) → Full context extraction
- **Campaign asset** (part of larger creative system) → Full Brief required

Extract at minimum:
- Subject (what to depict)
- Purpose (what this image must do)
- Platform/format (where it will appear)
- Style direction (or derive from concept)

**Output**: Completed brief (Quick or Full)

---

## STEP 2 — INTENT ANALYSIS

Translate the brief into creative intent:
- What must the viewer **feel** when they see this image?
- What must they **understand** without reading a caption?
- What must they **want to do** after seeing it?
- What would make this image **unforgettable** vs. merely good?

**Output**: Intent statement in one sentence per question above

---

## STEP 3 — CREATIVE CONTEXT MAPPING

**Reference**: `references/08-art-direction-system.md` (Part 1 — Creative Intelligence Analysis)

Analyze:
- Industry visual conventions (what does this category typically look like?)
- Audience visual language (what do they respond to?)
- Brand identity constraints (if established)
- Platform technical requirements

Run the **Originality Engine** (`references/08-art-direction-system.md`, Part 2):
1. Identify obvious visual approaches for this category
2. Identify overused AI patterns that must be avoided
3. Identify clichéd aesthetic combinations
4. Explore 2-3 alternatives
5. Find the distinctive visual signature

**Output**: Context analysis + initial creative direction

---

## STEP 4 — ART DIRECTION DEVELOPMENT

**Reference**: `references/08-art-direction-system.md` (Part 4-8)

Establish the complete visual language:

```
ART DIRECTION
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
Concept:        [The big idea in one sentence]
Composition:    [Rule + focal strategy + negative space]
Lighting:       [Source + direction + quality + color temperature]
Color Palette:  [Dominant + supporting + accent with rationale]
Materials:      [Surface qualities and their meaning]
Atmosphere:     [The feeling of the environmental world]
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
```

**Output**: Complete art direction specification

---

## STEP 5 — MULTI-DIRECTION EXPLORATION

*For significant projects only (key visuals, campaign heroes, brand imagery). Skip for simple requests.*

**Reference**: `references/08-art-direction-system.md` (Part 8)

Develop three genuinely different creative directions:

**Direction A — The Refined Classic**: Elegant, timeless, controlled
**Direction B — The Bold Experimental**: Unexpected, distinctive, unconventional
**Direction C — The Signature Masterpiece**: The recommended direction

For each, define: concept, composition, lighting, color, style, emotional impact, advantages, potential weaknesses.

**Output**: Three direction descriptions with recommendation

---

## STEP 6 — DIRECTION SELECTION & RATIONALE

Select the strongest direction and explain why it best serves the brief:
- Strongest concept alignment
- Highest originality score (without sacrificing clarity)
- Best audience fit
- Most technically achievable with available tools
- Best chance of making the viewer feel the target emotion

**Output**: Selected direction with 3-5 sentence rationale

---

## STEP 7 — TECHNICAL SPECIFICATION

**Reference**: `references/15-technical-standards.md` (IMAGE TECHNICAL STANDARDS)

Define all technical parameters:

```
TECHNICAL SPECIFICATION
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
Aspect Ratio:     [e.g., 16:9, 4:5, 1:1]
Resolution:       [e.g., 2560 × 1440px]
Color Space:      [sRGB / Display P3]
Output Format:    [PNG / JPG / WebP]
DPI:              [72 / 150 / 300]
Style:            [Photorealistic / Illustration / etc.]
Generator Target: [Midjourney / DALL-E / Flux / SD / etc.]
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
```

**Output**: Technical specification table

---

## STEP 8 — PROMPT CONSTRUCTION

**Reference**: `references/14-prompt-engineering.md`

Build the generation prompt using the RENDER BEAST Prompt Architecture:

**Layer 1 — Context Frame**: Style anchor and intent declaration
**Layer 2 — Subject**: Primary subject with full specification
**Layer 3 — Environment**: Setting, time, atmosphere
**Layer 4 — Composition**: Framing, focal strategy, perspective
**Layer 5 — Technical**: Camera, lens, lighting, color grade
**Layer 6 — Quality Anchors**: Technical quality statements

Adapt prompt structure to target generator (see `references/14-prompt-engineering.md`, Part 7).

```
GENERATION PROMPT
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
[Complete prompt, ready to use, formatted for target generator]
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
```

**Output**: Complete, formatted generation prompt

---

## STEP 9 — NEGATIVE PROMPT CONSTRUCTION

**Reference**: `references/14-prompt-engineering.md` (Part 10)

Build the negative prompt in three layers:
- **Universal**: watermark, low quality, artifacts, blur
- **Anti-slop**: generic ai aesthetic, stock photo composition, [specific banned patterns]
- **Style-specific**: [elements inconsistent with the chosen direction]

```
NEGATIVE PROMPT
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
[Complete negative prompt for target generator]
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
```

**Output**: Complete negative prompt

---

## STEP 10 — GENERATION EXECUTION

If a connected image generation tool is available:
1. Submit the prompt with technical parameters
2. Record the actual generation result
3. Do NOT claim success without actual output

If no connected tool:
1. Deliver prompt package clearly labeled as "PROMPT SPECIFICATION — requires generation tool"
2. Provide model recommendation and reasoning
3. Include any model-specific parameter recommendations

---

## STEP 11 — OUTPUT INSPECTION

*Only applicable when actual generation output is available.*

Inspect the generated image for:
- **Compositional accuracy**: Does it match the specified composition?
- **Subject accuracy**: Is the subject correctly depicted?
- **Lighting coherence**: Is the light consistent with the specification?
- **Material accuracy**: Do surfaces look as specified?
- **Technical quality**: Resolution, sharpness, artifact-free?

**Decision gate**:
- Acceptable → proceed to Anti-Slop Gate
- Minor issues → note for post-production
- Major issues → return to Step 8, adjust prompt, regenerate

---

## STEP 12 — ANTI-SLOP GATE

**Reference**: `references/13-anti-slop-quality-gates.md`

Run the complete Anti-Slop process:
1. **Detect** banned patterns in the output
2. **Diagnose** each detected pattern with specific critique
3. **Classify** severity (mild / moderate / severe / catastrophic)
4. **Decision**:
   - No slop detected → proceed
   - Mild → note and proceed
   - Moderate → targeted refinement before proceeding
   - Severe → prompt revision and regeneration
   - Catastrophic → reconceptualize direction

Run the Originality Test:
- [ ] This does not look like top Google Image results for this category
- [ ] This does not look like default AI output for this prompt
- [ ] There is at least one element that required a creative decision

Run the Intentionality Test:
- [ ] Every element present has a reason
- [ ] The composition was designed, not defaulted
- [ ] The color communicates meaning, not just aesthetics

**Output**: Anti-slop report with any identified issues and their resolution status

---

## STEP 13 — QUALITY SCORING

**Reference**: `evals/22-quality-evaluation.md`

Score the image across 11 categories:

| Category | Max | Score | Notes |
|---|---|---|---|
| Creative Originality | 15 | | |
| Art Direction | 15 | | |
| Composition | 10 | | |
| Visual Coherence | 10 | | |
| Craftsmanship | 10 | | |
| Technical Quality | 10 | | |
| Audience Relevance | 10 | | |
| User Experience | 5 | | |
| Accessibility | 5 | | |
| Production Readiness | 5 | | |
| Emotional Impact | 5 | | |
| **TOTAL** | **100** | | |

**Decision gate**:
- 95-100: MASTERPIECE — deliver with pride
- 90-94: WORLD-CLASS — deliver
- 85-89: PROFESSIONAL — deliver with minor notes
- 75-84: NEEDS REFINEMENT — do not deliver; execute Step 14
- Below 75: REJECT — return to Step 5 or 3

---

## STEP 14 — REFINEMENT ITERATION

*Only when quality score is below 85.*

Identify the lowest-scoring categories and their specific weaknesses.

**Improvement plan**:
```
IMPROVEMENT PLAN
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
Current Score: [X]/100
Target Score: 85+

Category Gaps:
- [Category]: [Current] → [Target] | Action: [Specific fix]
- [Category]: [Current] → [Target] | Action: [Specific fix]

Prompt Changes:
- [What to add/change/remove in the prompt]

Direction Changes (if needed):
- [Any conceptual revision needed]
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
```

Return to Step 8 (prompt revision) or Step 4 (art direction revision) as indicated.

**Maximum 3 iterations before escalating to full reconceptualization.**

---

## STEP 15 — POST-PRODUCTION INSTRUCTIONS

*Only when applicable — not all images require post-production.*

Specify any required post-production:
- Color corrections (direction and amount)
- Retouching (level and areas)
- Typography overlay (using Strategy 2 from `references/09-image-production.md`)
- Compositing (what elements to combine)
- Format conversion for delivery

**Output**: Post-production spec or "No post-production required"

---

## STEP 16 — FINAL DELIVERY PACKAGE

Compile the complete deliverable:

```
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
IMAGE BEAST — FINAL DELIVERY
[Project Name]
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

CREATIVE CONCEPT
[One paragraph — the big idea and why it serves the brief]

ART DIRECTION
[Description of the visual world and all major decisions]

GENERATION PROMPT
[Complete prompt, ready to use]

NEGATIVE PROMPT
[Complete negative prompt]

TECHNICAL PARAMETERS
Aspect Ratio: [X]
Resolution: [X]
Format: [X]
Generator: [X]

POST-PRODUCTION
[Instructions or "None required"]

QUALITY SCORE: [X]/100 — [LEVEL]

ASSUMPTIONS MADE
[List of creative decisions made where brief was ambiguous]

NEXT STEPS
[What to do with this — test variations, A/B test, production handoff]
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
```

---

## DECISION TREE SUMMARY

```
REQUEST RECEIVED
     │
     ├─ Simple → QUICK BRIEF → Steps 2,3,4,7,8,9 → DELIVER
     │
     ├─ Medium → QUICK BRIEF → Steps 2-4,7-12 → Quality Gate → DELIVER
     │
     └─ Significant → FULL BRIEF → All Steps → Quality Gate → DELIVER
                                                     │
                                              Score < 85?
                                                     │
                                              Yes → STEP 14 → ITERATE
                                              No → STEP 15-16 → DELIVER
```
