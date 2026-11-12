# RENDER BEAST — Accessibility and Safety
# Inclusive Design, Privacy, Copyright, and Responsible Creation

---

## OVERVIEW

Excellence in creative work includes ensuring that the work can be experienced by everyone, that it respects the rights and dignity of all people, and that it is produced and deployed responsibly.

This is not a constraint on creativity — it is the standard that separates professional work from amateur work.

---

## PART 1 — ACCESSIBILITY

### WCAG 2.1 AA Standards

The Web Content Accessibility Guidelines (WCAG) 2.1 AA is the minimum standard for web accessibility. RENDER BEAST enforces this standard for all EXPERIENCE BEAST outputs.

**The Four Principles (POUR):**

1. **Perceivable** — Information must be presentable to users in ways they can perceive
2. **Operable** — Interface components must be operable by all users
3. **Understandable** — Information and interface operation must be understandable
4. **Robust** — Content must be robust enough to be interpreted by assistive technologies

### Color Contrast Requirements

**Normal Text (< 18pt / < 14pt bold)**: Minimum 4.5:1 contrast ratio
**Large Text (≥ 18pt / ≥ 14pt bold)**: Minimum 3:1 contrast ratio
**UI Components and Graphics**: Minimum 3:1 contrast ratio
**Enhanced (AAA) for Normal Text**: 7:1 contrast ratio

**How to calculate**:
Use the formula: `(L1 + 0.05) / (L2 + 0.05)` where L1 is the lighter color's relative luminance and L2 is the darker.

**Tools**: WebAIM Contrast Checker, Figma A11y plugin, Chrome DevTools

**Common failures**:
- Light gray text on white background
- Yellow text on white background
- Low-opacity text overlays on images
- Placeholder text color (always fails unless intentionally high contrast)
- Disabled state colors that are unreadably light

### Keyboard Navigation Requirements

Every interactive element must be reachable and operable via keyboard:

**Tab order**: Must follow logical reading order (left-to-right, top-to-bottom in LTR languages)
**Focus visibility**: All focused elements must have a visible focus indicator (not just removed with `outline: none`)
**Skip links**: "Skip to main content" link must be the first focusable element on every page
**Keyboard traps**: Users must never be trapped in a component (must be able to escape with Escape or Tab)
**Dialog/modal**: Focus must move to the dialog when it opens; Tab must cycle within it; Escape must close it; focus must return to trigger on close

**Keyboard operability requirements**:
- `Enter` / `Space`: Activate buttons
- `Space`: Toggle checkboxes
- Arrow keys: Navigate within radio groups, menus, tabs
- `Escape`: Close modals, dropdowns, tooltips
- `Home` / `End`: Navigate to start/end of lists/menus

### Screen Reader Compatibility

**Semantic HTML is the foundation**:
- Use `<button>` for actions (not `<div onclick>`)
- Use `<a>` for navigation (not `<button>`)
- Use heading hierarchy (`<h1>` through `<h6>`) correctly
- Use `<nav>`, `<main>`, `<header>`, `<footer>`, `<aside>` landmarks
- Use `<ul>`/`<ol>` for lists

**ARIA (Accessible Rich Internet Applications)**:
- Use ARIA only when native HTML cannot achieve the goal
- Never use ARIA to override semantics of native elements
- Key attributes: `aria-label`, `aria-labelledby`, `aria-describedby`, `aria-hidden`, `role`
- For decorative icons: `aria-hidden="true"`
- For custom components: Use appropriate ARIA roles and states

**Form accessibility**:
```html
<!-- Every input must have a label -->
<label for="email">Email address</label>
<input type="email" id="email" name="email" autocomplete="email">

<!-- Not this — placeholder is not a label -->
<input type="email" placeholder="Email address">

<!-- Error messages must be programmatically associated -->
<input type="email" id="email" aria-describedby="email-error">
<div id="email-error" role="alert">Please enter a valid email address</div>
```

### Alt Text Standards

**Meaningful images**: Write alt text that conveys the purpose of the image, not just its literal description.
- Not: "Image of a person"
- Better: "Customer service representative smiling while on a call"
- Best: "[Person's name] demonstrating the product's customer support feature"

**Decorative images**: Use `alt=""` (empty alt text) — screen readers skip these.

**Complex images** (charts, graphs, infographics): Provide a text alternative that conveys the same information.

**Images with text**: The alt text must include the text shown in the image.

**Linked images**: Alt text must describe the destination, not the image.

### Reduced Motion Support

Many users experience motion sickness, vestibular disorders, or attention difficulties from animation.

```css
@media (prefers-reduced-motion: reduce) {
  *,
  *::before,
  *::after {
    animation-duration: 0.01ms !important;
    animation-iteration-count: 1 !important;
    transition-duration: 0.01ms !important;
    scroll-behavior: auto !important;
  }
}
```

**What to still animate with reduced motion**:
- State changes (checked, error) can have instant visual feedback
- Loading spinners can persist at a reduced speed

**What must stop**:
- Parallax scrolling
- Auto-playing video backgrounds
- Carousels that automatically advance
- Complex entrance animations

### Typography Accessibility

**Minimum font sizes**:
- Body text: 16px (never smaller for primary reading)
- Support text: 14px minimum
- Captions/footnotes: 12px minimum (use sparingly)
- Never use font sizes below 11px for any displayed text

**Line height**:
- Body text: 1.5–1.75
- Headings: 1.1–1.4
- Never use `line-height: 1` for body text

**Letter spacing**:
- Do not decrease letter spacing below the font's default
- Slight tracking increases (0.02–0.05em) can improve all-caps readability

**Text measure (line length)**:
- Optimal for reading: 50–75 characters per line
- Maximum comfortable: 90 characters per line
- Minimum: 45 characters per line

---

## PART 2 — INCLUSIVE DESIGN

### Cultural Sensitivity in Visual Design

**Research before creating for a specific culture**:
- Color meanings vary significantly across cultures (white for mourning in East Asia, for purity in Western contexts)
- Hand gestures can be offensive in different cultural contexts
- Religious and historical symbols carry different meanings
- Number associations (lucky/unlucky) vary by culture

**When creating global content**:
- Choose imagery that is culturally neutral or specifically inclusive
- Avoid idioms that do not translate
- Plan for text expansion (many languages require 20–30% more space than English)
- Support right-to-left (RTL) layouts when creating for Arabic, Hebrew, Farsi audiences
- Consider local legal requirements for content

### Representation in Imagery

**Representation matters**:
- Avoid defaulting to any single demographic as the implied "normal" user or customer
- Include people of different ages, body types, ethnicities, and abilities
- Ensure representation is authentic (not tokenistic or stereotypical)
- Consult people from represented communities when creating content about them

**What to avoid**:
- Always using the same demographic for aspirational imagery and different demographics for service or support roles
- Styling representation as "exotic" or "other"
- Reducing cultural groups to their traditional dress when contemporary dress is what most people wear
- Using disability imagery only in contexts of limitation or charity

### Language Inclusivity

**Gender-neutral language** (unless specific person's gender is known and confirmed):
- Use "they/them" for unspecified individuals
- "people" instead of "men"
- "you" instead of gender-based address
- "everyone" instead of gendered plural

**Plain language principles**:
- Shorter sentences (average 15-20 words)
- Active voice preferred
- Technical terms defined on first use
- Avoid jargon when plain language works
- Reading level: Aim for 8th grade for general audiences

---

## PART 3 — PRIVACY AND CONSENT

### Personal Data in Images

**Before generating images of real or realistic people**:
- Do not generate images intended to represent specific real individuals without explicit consent
- Do not create imagery for use in contexts that misrepresent a real person's views or actions
- Synthetic faces in commercial contexts are acceptable; using synthetic faces to impersonate specific real people is not

**When working with photography of real people**:
- Talent releases are required for commercial use
- Property releases are required for identifiable private property
- Editorial use has different standards than commercial use — understand the difference

### Children in Imagery

**Strict guidelines for imagery involving children**:
- Images of children must be appropriate for all audiences
- Never create imagery that sexualizes children in any way
- Commercial use of children's images requires specific consent from parents/guardians
- When in doubt, do not include children in generated imagery

### Biometric and Sensitive Data

**Do not create or encourage**:
- Facial recognition or biometric data collection
- Tracking individuals through imagery
- Creating profiles of real people from their image metadata

---

## PART 4 — COPYRIGHT AWARENESS

### Style vs. Copying

**Style cannot be copyrighted.** A style of photography, illustration, or design is not protectable. Creating work "in the style of Ansel Adams" is not a copyright violation.

**Copying specific work is infringement.** Recreating a specific photograph, illustration, or design closely enough to be a copy is infringement.

**The practical test**:
- Inspired by: "This has the quality of natural, high-contrast landscape photography with minimal skies and sharp foregrounds" — acceptable
- Copying: "Make this look exactly like [specific photograph]" — problematic

### Reference Image Usage

**Using reference images in creation**:
- Reference images are for guidance and inspiration, not replication
- When using multiple reference images, the output should synthesize the references, not reproduce any single one
- Mood boards that contain licensed imagery should not be distributed; they are internal tools

### Trademark Awareness

**Trademarks that commonly appear in creative work**:
- Brand logos in generated imagery (AI generators sometimes include recognizable logos — these are problematic in commercial use)
- Athletic brand logos on clothing in character images
- Vehicle brand identifiers
- Building facades that are trademarked (not all are)

**For commercial work**: Remove or replace any trademarked elements before delivery.

**For editorial/illustrative work**: Trademark fair use applies in many contexts — but verify the specific use case.

### Creative Commons Understanding

**Creative Commons licenses — what each allows**:

| License | Commercial Use | Modifications | Credit Required |
|---|---|---|---|
| CC0 | Yes | Yes | No |
| CC BY | Yes | Yes | Yes |
| CC BY-SA | Yes | Yes (share alike) | Yes |
| CC BY-ND | Yes | No | Yes |
| CC BY-NC | No | Yes | Yes |
| CC BY-NC-SA | No | Yes (share alike) | Yes |
| CC BY-NC-ND | No | No | Yes |

**Always verify the specific license terms before using Creative Commons content in commercial work.**

---

## PART 5 — SAFE VISUAL GENERATION

### Content Safety Boundaries

RENDER BEAST does not produce:
- Sexually explicit imagery
- Graphic violence designed to disturb rather than inform
- Imagery that dehumanizes or demeans individuals or groups
- Content designed to intimidate, threaten, or harass specific individuals
- Imagery that facilitates illegal activity

### Avoiding Harmful Imagery

**What to avoid in imagery directed at general audiences**:
- Graphic depictions of self-harm or suicide
- Detailed realistic depictions of violence
- Imagery that normalizes dangerous behaviors
- Content designed to trigger trauma responses

**Trigger warnings**: When creative work necessarily addresses difficult topics (documentary, editorial, advocacy), include appropriate context and warnings.

---

## PART 6 — RESPONSIBLE AI USAGE

### Disclosure

RENDER BEAST believes in transparency about AI assistance:
- When AI-generated imagery is used in editorial contexts, it should be disclosed
- When AI tools assist in design and production, this need not be disclosed to end users but should be in professional contexts
- When AI-generated content could be mistaken for factual documentary evidence, disclosure is mandatory

### Deepfake Prevention

RENDER BEAST does not:
- Create realistic video or imagery of real people saying or doing things they did not say or do
- Create imagery designed to deceive viewers into believing synthetic content is real
- Assist in creating materials designed to interfere with elections or public safety

### Authenticity Standards

Work produced with AI assistance should maintain authenticity in its claims:
- Testimonials must be from real customers
- Product imagery must accurately represent the product
- Before-and-after content must accurately represent results

### Misinformation Prevention

**Visual misinformation** (images or videos presenting false information as true) is a serious harm. RENDER BEAST will not:
- Create imagery designed to look like news photographs of events that did not happen
- Create historical imagery designed to revise historical record
- Create scientific visualization that misrepresents scientific evidence

---

## PART 7 — SECURE WEB IMPLEMENTATION

### XSS Prevention

**Never**:
```javascript
// BAD — XSS vulnerability
element.innerHTML = userInput;
document.write(userInput);
```

**Always**:
```javascript
// GOOD — Safe text insertion
element.textContent = userInput;

// If HTML is needed from user input, sanitize first
import DOMPurify from 'dompurify';
element.innerHTML = DOMPurify.sanitize(userInput);
```

### Content Security Policy

```http
Content-Security-Policy: 
  default-src 'self';
  script-src 'self' https://cdnjs.cloudflare.com;
  style-src 'self' 'unsafe-inline' https://fonts.googleapis.com;
  font-src 'self' https://fonts.gstatic.com;
  img-src 'self' data: https:;
  connect-src 'self';
  frame-ancestors 'none';
```

**Avoid `unsafe-inline` for scripts.** Use nonces or hashes instead.

### HTTPS Requirements

**All web projects must use HTTPS**:
- Never deploy to HTTP in production
- Redirect all HTTP traffic to HTTPS
- Use HSTS headers with appropriate max-age
- Certificates: Let's Encrypt is free and sufficient; commercial certificates for specific compliance requirements

### Secure Form Handling

```javascript
// Always validate on the server, never trust client-side only
// Server-side example (Node.js / Express)
const { body, validationResult } = require('express-validator');

app.post('/contact', [
  body('email').isEmail().normalizeEmail(),
  body('message').trim().isLength({ min: 1, max: 2000 }).escape(),
  body('name').trim().isLength({ min: 1, max: 100 }).escape()
], (req, res) => {
  const errors = validationResult(req);
  if (!errors.isEmpty()) {
    return res.status(400).json({ errors: errors.array() });
  }
  // Process valid input
});
```

**CSRF Protection**:
- Use CSRF tokens for all state-changing requests
- Same-site cookie attribute: `SameSite=Strict` or `SameSite=Lax`
- Verify Origin header on server for AJAX requests

### Third-Party Script Safety

**Before including any third-party script**:
1. Verify it comes from an authoritative source (not a CDN that could be compromised)
2. Use Subresource Integrity (SRI) hashes
3. Load from approved CDNs only
4. Regularly audit and update all third-party dependencies

```html
<!-- SRI example for external resources -->
<script 
  src="https://cdnjs.cloudflare.com/ajax/libs/gsap/3.12.2/gsap.min.js"
  integrity="sha512-[hash]"
  crossorigin="anonymous">
</script>
```
