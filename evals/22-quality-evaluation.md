# RENDER BEAST — Quality Evaluation Framework
# 100-Point Scoring System

---

## OVERVIEW

Every major RENDER BEAST deliverable is evaluated against this 100-point framework before delivery. The evaluation is honest — it reflects the actual quality of the work, not the effort that went into it.

**When evaluating a specification** (no actual render available): Score the specification and label it "SPECIFICATION SCORE — not a render evaluation."

**When evaluating actual output**: Score the rendered/generated result and label it "OUTPUT SCORE."

---

## THE 100-POINT SCORING SYSTEM

### CATEGORY 01 — CREATIVE ORIGINALITY (15 Points)

**What it measures**: The degree to which the creative direction is distinctive, non-generic, and specific to this brief.

**Scoring Rubric**:

| Score | Standard | Description |
|---|---|---|
| 14-15 | MASTERPIECE | The creative direction is unmistakably specific to this brief and would be notable in any context. No generic patterns. The distinctive element is memorable. |
| 11-13 | WORLD-CLASS | The creative direction is significantly more original than category conventions. Clear evidence of genuine creative thinking. |
| 9-10 | PROFESSIONAL | Avoids most generic patterns. Has at least one distinctive creative decision. Generally original within the category. |
| 6-8 | NEEDS REFINEMENT | Some original elements but several generic patterns remain. Could be confused with similar work in the category. |
| 3-5 | WEAK | Primarily relies on category conventions and generic patterns. Little evidence of creative thinking specific to this brief. |
| 0-2 | REJECT | Entirely generic. This output could have been created by any basic AI prompt without creative direction. |

**Anti-slop override**: If any pattern from the Banned Pattern Registry appears without creative justification, the maximum score for this category is 7.

---

### CATEGORY 02 — ART DIRECTION (15 Points)

**What it measures**: The quality of the visual language decisions — composition, color, typography, lighting, materials, atmosphere.

**Scoring Rubric**:

| Score | Standard | Description |
|---|---|---|
| 14-15 | MASTERPIECE | Every visual decision is deliberate and serves the concept. The visual language is coherent, distinctive, and communicates meaning before any text is read. |
| 11-13 | WORLD-CLASS | Strong visual language with clear creative intent. Most decisions are purposeful. The composition, color, and lighting work together. |
| 9-10 | PROFESSIONAL | Clear visual direction. Good decisions in the main elements. Some secondary decisions could be stronger. |
| 6-8 | NEEDS REFINEMENT | The visual direction is identifiable but inconsistent. Some strong decisions mixed with weak ones. |
| 3-5 | WEAK | Visual decisions are primarily default choices. No clear visual language. Elements don't support each other. |
| 0-2 | REJECT | No discernible art direction. Random visual choices with no coherent visual language. |

---

### CATEGORY 03 — COMPOSITION (10 Points)

**What it measures**: The structural organization of the visual frame or layout — focal point, hierarchy, balance, movement of the eye.

**Scoring Rubric**:

| Score | Standard | Description |
|---|---|---|
| 10 | MASTERPIECE | The composition is designed. The eye moves through the work in a deliberate sequence that serves the communication goal. The focal point is unambiguous. |
| 8-9 | WORLD-CLASS | Strong composition with clear focal strategy. Visual weight is appropriately distributed. |
| 6-7 | PROFESSIONAL | Good composition that serves the work. Eye-flow is clear. No major compositional problems. |
| 4-5 | NEEDS REFINEMENT | Composition is identifiable but has weaknesses — unclear focal point, competing elements, or accidental tension. |
| 2-3 | WEAK | Composition is unresolved. Multiple focal points compete. Visual weight is unbalanced without intent. |
| 0-1 | REJECT | No compositional structure. Random element placement. |

**Discipline-specific notes**:
- **Image**: Check focal point, rule, negative space, depth
- **Video**: Check shot composition, sequence rhythm, editorial flow
- **3D**: Check camera angle, subject framing, environment composition
- **Web**: Check layout hierarchy, section flow, visual weight distribution

---

### CATEGORY 04 — VISUAL COHERENCE (10 Points)

**What it measures**: The consistency and coherence of the visual language across all elements — style, color, typography, lighting, texture.

| Score | Standard | Description |
|---|---|---|
| 10 | MASTERPIECE | The work is completely coherent. Every element belongs to the same visual world. Nothing is out of place. |
| 8-9 | WORLD-CLASS | High coherence throughout. No jarring inconsistencies. The visual language is consistent. |
| 6-7 | PROFESSIONAL | Generally coherent with minor inconsistencies that don't significantly undermine the work. |
| 4-5 | NEEDS REFINEMENT | Some areas are coherent but significant inconsistencies exist — style mixing, lighting contradictions, color temperature issues. |
| 2-3 | WEAK | Multiple significant inconsistencies. The work feels assembled rather than designed. |
| 0-1 | REJECT | No coherence. Elements appear to be from different visual worlds assembled without integration. |

---

### CATEGORY 05 — CRAFTSMANSHIP (10 Points)

**What it measures**: The technical execution quality — the degree to which the work shows mastery of its medium.

| Score | Standard | Description |
|---|---|---|
| 10 | MASTERPIECE | Executed with exceptional skill. Every detail is precisely rendered. No technical weaknesses. |
| 8-9 | WORLD-CLASS | High technical quality throughout. Very minor imperfections that most viewers would not notice. |
| 6-7 | PROFESSIONAL | Technically sound. Craft is evident. Some areas could be refined with more effort. |
| 4-5 | NEEDS REFINEMENT | Technical weaknesses are visible and affect the perception of quality. |
| 2-3 | WEAK | Multiple technical problems undermine the work significantly. |
| 0-1 | REJECT | Technical failures that make the work unusable. |

**Discipline-specific craft indicators**:
- **Image**: Lighting quality, sharpness, color rendering, compositional execution
- **Video**: Shot steadiness, focus accuracy, color consistency, editorial timing
- **3D**: Topology quality, UV mapping, material rendering, lighting setup
- **Web**: Code quality, responsive behavior, interaction smoothness, accessibility

---

### CATEGORY 06 — TECHNICAL QUALITY (10 Points)

**What it measures**: Whether the work meets technical production standards for its intended use.

| Score | Standard | Description |
|---|---|---|
| 10 | MASTERPIECE | Exceeds technical requirements. Production-ready without modification. |
| 8-9 | WORLD-CLASS | Meets all technical requirements. No significant technical issues. |
| 6-7 | PROFESSIONAL | Meets minimum technical requirements. Some specifications could be improved. |
| 4-5 | NEEDS REFINEMENT | Meets some technical requirements but falls short in important areas. |
| 2-3 | WEAK | Significant technical shortfalls that limit usability in the intended context. |
| 0-1 | REJECT | Technical failures that prevent use in the intended context. |

**Category-specific requirements**:
- **Image**: Resolution, color space, format, compression quality
- **Video**: Resolution, frame rate, codec, color grade, audio specifications
- **3D**: Polygon count, UV mapping, texture resolution, file format, export correctness
- **Web**: Core Web Vitals, accessibility standards, responsive correctness, security

**Critical override**: Any critical technical failure (broken accessibility, XSS vulnerability, broken responsive layout, corrupted 3D export) caps this category at 3 regardless of other qualities.

---

### CATEGORY 07 — AUDIENCE RELEVANCE (10 Points)

**What it measures**: How well the work speaks to its specific target audience.

| Score | Standard | Description |
|---|---|---|
| 10 | MASTERPIECE | The audience would immediately recognize this as being specifically for them. It speaks their visual language and addresses their specific values and aspirations. |
| 8-9 | WORLD-CLASS | Strongly connects with the target audience. Clear evidence that the audience's perspective informed creative decisions. |
| 6-7 | PROFESSIONAL | Appropriate for the audience. Would be received positively. |
| 4-5 | NEEDS REFINEMENT | Appropriate but generic — could be for many audiences. The specific audience's perspective is not clearly reflected. |
| 2-3 | WEAK | Mismatches the audience in one or more significant ways. |
| 0-1 | REJECT | Fundamentally misaligned with the target audience. |

---

### CATEGORY 08 — USER EXPERIENCE (5 Points)

**What it measures**: For web and interactive work, the quality of the user experience. For other media, the ease and pleasure of experiencing the work.

| Score | Standard | Description |
|---|---|---|
| 5 | MASTERPIECE | Effortless to experience. The user/viewer's journey through the work is intuitive, pleasurable, and productive. |
| 4 | WORLD-CLASS | Very good experience. Minimal friction. Clear pathways. |
| 3 | PROFESSIONAL | Good experience. Some friction points that could be improved. |
| 2 | NEEDS REFINEMENT | Experience has notable friction. Users/viewers would have difficulty or frustration. |
| 0-1 | WEAK/REJECT | Poor experience. Users/viewers cannot accomplish their goals. |

**For web specifically**: Keyboard navigation, loading states, error handling, mobile experience.

---

### CATEGORY 09 — ACCESSIBILITY (5 Points)

**What it measures**: For web work, WCAG 2.1 AA compliance. For other media, inclusion and representation.

| Score | Standard | Description |
|---|---|---|
| 5 | MASTERPIECE | Fully WCAG 2.1 AA compliant (web) or exemplifies inclusive representation (other media). |
| 4 | WORLD-CLASS | Near-complete compliance/inclusion. Minor non-critical gaps. |
| 3 | PROFESSIONAL | Generally compliant/inclusive with specific areas needing attention. |
| 2 | NEEDS REFINEMENT | Several accessibility failures that affect real users. |
| 0-1 | WEAK/REJECT | Fundamental accessibility failures. |

**Critical override**: Any WCAG 2.1 AA failure that blocks assistive technology users from core content or functions caps the total score at 75 regardless of other scores.

---

### CATEGORY 10 — PRODUCTION READINESS (5 Points)

**What it measures**: Whether the deliverable is complete and ready for the next production step without additional work.

| Score | Standard | Description |
|---|---|---|
| 5 | MASTERPIECE | Complete, clearly documented, ready for immediate use. No assumptions or gaps. |
| 4 | WORLD-CLASS | Complete with minor documentation gaps that don't affect use. |
| 3 | PROFESSIONAL | Ready for use with some minor items to address. |
| 2 | NEEDS REFINEMENT | Incomplete — significant preparation needed before production use. |
| 0-1 | WEAK/REJECT | Not production-ready. Major preparation or completion work needed. |

---

### CATEGORY 11 — EMOTIONAL IMPACT (5 Points)

**What it measures**: Whether the work makes the viewer feel something specific and appropriate to the brief.

| Score | Standard | Description |
|---|---|---|
| 5 | MASTERPIECE | Creates a distinct, specific emotional response that serves the communication goal. Memorable. |
| 4 | WORLD-CLASS | Clear emotional quality that is appropriate and effective for the brief. |
| 3 | PROFESSIONAL | Has emotional quality. Viewer feels something, though it may not be fully realized. |
| 2 | NEEDS REFINEMENT | Emotional response is weak or inconsistent. Work does not particularly move the viewer. |
| 0-1 | WEAK/REJECT | No discernible emotional impact. Viewer feels nothing specific. |

---

## QUALITY LEVELS

| Total Score | Level | Meaning | Action |
|---|---|---|---|
| 95–100 | MASTERPIECE LEVEL | Exceptional work | Deliver with pride |
| 90–94 | WORLD-CLASS | Outstanding | Deliver |
| 85–89 | PROFESSIONAL | High quality | Deliver with minor notes |
| 75–84 | NEEDS REFINEMENT | Acceptable quality | Mandatory improvement plan required |
| 60–74 | WEAK | Below acceptable | Do not deliver; major revision |
| Below 60 | REJECT AND REBUILD | Fundamental problems | Restart from concept phase |

---

## MANDATORY QUALITY GATE

**When score is below 85**, provide this mandatory improvement plan before any delivery:

```
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
MANDATORY IMPROVEMENT PLAN
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
Current Score: [X]/100
Target Score: 85+
Point Gap: [X] points

PRIORITY IMPROVEMENTS:

#1 — [Category] [Current]/[Max] → Target [X]/[Max]
Problem: [Specific, concrete description of the weakness]
Fix: [Specific, actionable improvement]
Impact: +[X] points

#2 — [Category] [Current]/[Max] → Target [X]/[Max]
Problem: [Specific description]
Fix: [Specific action]
Impact: +[X] points

[Continue for each category below target]

IMPLEMENTATION ORDER:
1. [Do this first — highest impact]
2. [Then this]
3. [Then this]

REVISED ESTIMATE AFTER IMPROVEMENTS:
Score after improvements: [X]/100 — [LEVEL]
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
```

---

## REJECTION CONDITIONS

These conditions automatically trigger rejection, regardless of overall score:

**ZERO-TOLERANCE VIOLATIONS** — Any of these = automatic reject:

- **Explicit content** in work not for adult platforms
- **XSS vulnerability** in web implementation
- **Broken responsive layout** that makes mobile unusable
- **Missing ARIA** that completely blocks screen reader access to primary content
- **Placeholder content** in final deliverable (Lorem ipsum, "image here", "coming soon" for existing features)
- **Fake testimonials** or fabricated user reviews
- **Copyright infringement** — directly copying specific protected work
- **Claiming generated output exists** when no generation tool was available
- **Critical browser console errors** in web deliverable
- **3D export corruption** that prevents file opening

---

## DISCIPLINE-SPECIFIC EVALUATION ADJUSTMENTS

### Image Evaluation Nuances

**When evaluating image prompts** (no actual generation available):
- Evaluate the specification quality, not imagined output
- Score Composition based on specified compositional strategy
- Score Technical Quality based on specified parameters
- Cap maximum "Craftsmanship" at 8 (cannot fully evaluate without render)
- Cap maximum "Emotional Impact" at 4 (cannot fully evaluate without render)

**When evaluating actual generated images**:
- Lighting coherence is a critical indicator — incoherent light scores maximum 5 for Craftsmanship
- Accidental elements (extra limbs, merged objects) cap Composition at 5
- Generational artifacts (blur, smearing, banding) cap Technical Quality at 5

**What moves Originality score up for images**:
- Unexpected but purposeful compositional choice
- Color palette that communicates meaning beyond "looks good"
- Lighting quality that tells us something about the world
- Subject has history and specificity

### Video Evaluation Nuances

**When evaluating video specifications** (no clips available):
- Evaluate based on TIMELINE ENGINE quality and shot list specificity
- Score the quality of the creative concept and narrative architecture
- Cap "Craftsmanship" and "Technical Quality" at 7 (cannot evaluate without clips)

**When evaluating actual video clips**:
- Continuity breaks between clips are severe — cap Visual Coherence at 5
- Generic color grade without concept — cap Art Direction at 7
- Unmotivated slow motion — cap Creative Originality at 7
- Each clip is evaluated individually AND as part of the sequence

**What moves Originality score up for video**:
- Shot choices that reflect a specific point of view
- Editorial rhythm driven by emotion, not habit
- Sound design that adds meaning beyond matching the visual
- One shot or moment that only this film could contain

### 3D Evaluation Nuances

**When evaluating 3D specifications or code**:
- Score implementation completeness and technical accuracy
- Score geometry and material specification quality
- Adjust "Emotional Impact" to reflect the render quality potential

**When evaluating actual renders**:
- Material accuracy to PBR specification is critical
- Lighting that reveals form vs. hides it
- Polygon budget adherence relative to target use case

**What moves Originality score up for 3D**:
- Silhouette that is distinctive and readable
- Material choices that communicate character
- Lighting that tells a story about the object's context
- Details that have a reason for being there

### Website Evaluation Nuances

**Website has mandatory additional checks**:
- If WCAG 2.1 AA fails significantly → maximum total score = 75
- If responsive layout is broken on mobile → maximum total score = 75
- If Core Web Vitals fail (LCP > 4s) → cap Technical Quality at 4
- If forms don't work → cap Production Readiness at 2

**UX weighted heavier for web**:
- For web projects, User Experience carries 10 effective points (the 5 allocated + 5 redistributed from areas that don't apply)

**What moves Originality score up for websites**:
- Visual identity that is specific to this brand, not the category
- Navigation that is designed for this site's content, not the generic pattern
- Feature section that uses a format appropriate to these specific features
- Typography hierarchy that reflects the brand's voice

---

## TEST SCENARIOS

### IMAGE TEST SCENARIO
**Input**: "Create a product image for a premium matcha tea brand targeting health-conscious millennials"

**Evaluation focus**:
- Creative Originality: Does it avoid the generic "zen aesthetic" (bamboo, stone, muted green, Japanese calligraphy) unless that's truly the strongest direction?
- Art Direction: Does the visual language communicate health AND premium AND millennial identity simultaneously?
- Audience Relevance: Would a millennial health-conscious consumer feel "this is for me"?
- Expected score for excellent work: 88-93

**Common failure points**:
- Defaulting to white-on-white studio product shot (generic)
- Defaulting to Japanese aesthetic clichés (generic)
- Color palette that is "natural/earthy" without a specific concept (weak art direction)

### VIDEO TEST SCENARIO
**Input**: "Create a 30-second brand commercial for a sustainable athletic wear startup"

**Evaluation focus**:
- Creative Originality: Does it avoid the "athlete training, music swells, logo" formula?
- Emotional Arc: Is there a clear emotional progression that the viewer feels?
- Cinema Beast craft: Are the shot choices motivated? Is the edit driven by emotion?
- Expected score for excellent work: 85-91

**Common failure points**:
- Generic "inspirational" commercial formula
- Unmotivated slow motion
- Color grade that is "cinematic" without being specific to the story

### 3D TEST SCENARIO
**Input**: "Create a 3D product visualization for a futuristic gaming headset"

**Evaluation focus**:
- Creative Originality: Does it avoid dark background + floating particles + neon accent lines?
- Dimension Beast craft: Geometry specification quality, material PBR values, lighting design
- Technical Quality: Polygon budget, UV specification, format correctness
- Expected score for excellent work: 85-90

**Common failure points**:
- Generic sci-fi environment (dark + neon + floating particles)
- Over-smooth plastic material on everything
- Lighting that looks like default three-point setup without creative intent

### WEBSITE TEST SCENARIO
**Input**: "Create a landing page for a B2B project management SaaS tool"

**Evaluation focus**:
- Creative Originality: Does it avoid the universal SaaS template?
- Experience Beast craft: Is the visual identity specific? Does the layout serve this content?
- Technical Quality: Accessibility, responsive, performance
- Expected score for excellent work: 85-92

**Common failure points**:
- Generic SaaS hero section (gradient + headline + feature cards)
- Generic pricing table design
- Identical card components for all features regardless of their nature
- Mobile layout that is just stacked desktop layout

---

## REFINEMENT PROCEDURES

### Improving a 75 to 85+

The 10 points needed to reach 85 from 75 typically come from:

**Most impactful categories** (fix these first):
1. Creative Originality (up to 15 pts available, often the most underperforming)
2. Art Direction (up to 15 pts available)
3. Composition (up to 10 pts)
4. Visual Coherence (up to 10 pts)

**Improvement framework for each category**:

For **Creative Originality**:
- Identify which generic patterns are present
- Apply Mutation Engine (`references/13-anti-slop-quality-gates.md`)
- Find the specific creative decision this brief deserves

For **Art Direction**:
- Establish the visual language from concept, not from defaults
- Make each visual decision deliberate: Why this color? Why this light? Why this composition?
- Ensure all elements of the visual language support each other

For **Composition**:
- Identify the primary focal point and ensure it is unambiguous
- Remove competing elements or subordinate them clearly
- Design the eye movement through the work

For **Visual Coherence**:
- Identify all inconsistencies (lighting, color temperature, style mixing)
- Choose one clear visual language and apply it consistently
- Remove any element that belongs to a different visual world

### Improvement Tracking

Track each iteration:

```
ITERATION LOG
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
Iteration 1:
  Score: [X]/100
  Changes made: [What was changed]
  Impact: +[X] points

Iteration 2:
  Score: [X]/100
  Changes made: [What was changed]
  Impact: +[X] points

Final Score: [X]/100 — [LEVEL]
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
Maximum 3 iterations before reconceptualizing direction.
```
