# RENDER BEAST — Website Workflow
# EXPERIENCE BEAST Step-by-Step Production Pipeline

---

## OVERVIEW

EXPERIENCE BEAST builds digital products that work — not websites that look good in screenshots. The workflow begins with positioning and audience, establishes a distinctive visual identity, then implements with technical excellence.

The fundamental rule: Never produce the same generic website structure for different clients. Every brief demands its own design language.

---

## STEP 1 — BRIEF INTAKE → EXPERIENCE BEAST

**Reference**: `workflows/17-intake-and-brief.md`

Classify the project:

| Type | Scope | Deliverable |
|---|---|---|
| Landing page | Single page | HTML/React implementation |
| Marketing site | 3-10 pages | Architecture + key page implementations |
| Web application | Multiple views | Architecture + component system + key views |
| Dashboard | Data-heavy | Layout system + component library |
| E-commerce | Product/cart/checkout | System architecture + key flows |

Extract at minimum:
- What the product/service/brand is
- Who the audience is
- What action must the visitor take
- Platform constraints (framework requirements, hosting, integrations)
- Existing brand assets (Y/N — if Y, describe)
- Technical constraints (must use specific tech, integrate with specific system)

---

## STEP 2 — PRODUCT POSITIONING ANALYSIS

Establish the competitive context:
- What category does this product compete in?
- What are the top 3-5 competitors' websites?
- What visual language dominates the category?
- Where is the opportunity to differ meaningfully?
- What would make this website immediately recognizable as different from competitors?

**Anti-slop check**: Is this category dominated by a visual cliché (all SaaS products use the same gradient hero + card features pattern)? If yes, what is a genuinely different approach?

**Output**: Positioning analysis with differentiation opportunity

---

## STEP 3 — USER JOURNEY MAPPING

For each primary user type, map the path through the site:

```
USER JOURNEY MAP
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
User Type: [Primary visitor persona]
Entry Point: [How they arrive — search, ad, referral, direct]

Journey:
  Arrival → [What they see first / what question is immediately answered]
  → [Next step — navigation, scroll, click]
  → [Information needed to continue]
  → [Decision point — qualify or leave]
  → [Conversion action — sign up, purchase, contact, download]
  → [Post-conversion — confirmation, next step, what happens now]

Success: [What "converted" looks like]
Failure Points: [Where they typically leave and why]
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
```

Map at least: primary journey, conversion journey, and mobile journey (which may differ significantly).

**Output**: User journey maps for primary paths

---

## STEP 4 — INFORMATION ARCHITECTURE

Structure the content hierarchy:

**Step 1 — Content Inventory**: List every piece of content that needs to exist on the site
**Step 2 — Content Grouping**: Group related content
**Step 3 — Priority Assignment**: Rank each group by importance to the primary user journey
**Step 4 — Navigation Structure**: Derive the navigation from the priority structure
**Step 5 — Sitemap**: Document the final page structure

```
SITEMAP
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
HOME
├── [Primary content priority 1]
│   └── [Detail page]
├── [Primary content priority 2]
│   ├── [Detail A]
│   └── [Detail B]
├── [Secondary content]
├── [Conversion page]
└── [Support pages]
    ├── About
    ├── Contact
    └── Legal
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
```

**Output**: Complete sitemap with page priorities

---

## STEP 5 — CONTENT STRATEGY

For each priority page, define:
- **Primary message**: One sentence this page must communicate
- **Supporting messages**: 2-3 secondary points
- **Content types**: Text, imagery, video, data, testimonials, etc.
- **Call to action**: The one thing the user should do on this page
- **SEO intent**: What query brings people here? What do they want to find?

**Copy direction** (if writing copy):
- Tone: [Specific voice — not "professional" but "confident and human, like explaining to a smart friend"]
- Reading level: [Target — for general audience: 8th grade]
- Terminology: [Industry jargon to use / avoid]

**Output**: Content strategy per page

---

## STEP 6 — CONTENT STRATEGY

*Establish the complete visual identity before writing any code.*

**Reference**: `references/08-art-direction-system.md`, `references/12-web-experience.md`

This is the most critical step. Run the **Originality Engine**:
1. What visual language dominates this category?
2. What patterns are overused?
3. What would be genuinely different and still serve the brief?

Establish:

```
VISUAL IDENTITY SYSTEM
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
CONCEPT: [The visual idea in one sentence]

TYPOGRAPHY SYSTEM:
  Display font: [Name + weight + character description]
  Body font: [Name + weight + character description]
  Mono font: [Name — if used for code, data, or detail]
  Type scale: [Custom or Tailwind-based]

COLOR SYSTEM:
  Primary: [Hex + rationale — why this color for this brand]
  Secondary: [Hex + rationale]
  Accent: [Hex + rationale]
  Background: [Hex or gradient]
  Surface: [Hex — card/component backgrounds]
  Text primary: [Hex]
  Text secondary: [Hex]
  Semantic colors: [Success/Warning/Error/Info]

SPACING SYSTEM:
  Base unit: [4px / 8px]
  Scale: [Token names and values]

VISUAL LANGUAGE:
  Border radius: [None/small/medium/large/pill]
  Shadow style: [None/subtle/medium/strong/colored]
  Border style: [None/thin/themed]
  Imagery style: [Photography direction or illustration style]
  Icon style: [Line/solid/duotone, weight, style]
  Motion style: [Minimal/moderate/expressive]

DISTINCTIVE ELEMENT:
  [The one visual decision that makes this design recognizable]
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
```

**Output**: Complete visual identity system

---

## STEP 7 — DESIGN SYSTEM CREATION

**Reference**: `references/12-web-experience.md` (Part 1 — Design Architecture, points 7-9)

Create the token-to-component hierarchy:

**Design Tokens** (CSS custom properties or Tailwind config):
```css
:root {
  /* Typography */
  --font-display: '[Font Name]', sans-serif;
  --font-body: '[Font Name]', sans-serif;
  
  /* Colors */
  --color-primary: #[HEX];
  --color-primary-hover: #[HEX];
  --color-background: #[HEX];
  --color-surface: #[HEX];
  --color-text: #[HEX];
  --color-text-secondary: #[HEX];
  
  /* Spacing */
  --space-unit: 4px;
  /* Full scale */
  
  /* Border radius */
  --radius-sm: Xpx;
  --radius-md: Xpx;
  --radius-lg: Xpx;
  
  /* Shadows */
  --shadow-sm: X;
  --shadow-md: X;
  --shadow-lg: X;
}
```

**Component Library** (priority order):
1. Button (primary, secondary, ghost, destructive)
2. Input / Textarea / Select (all states)
3. Card / Panel
4. Navigation (desktop + mobile)
5. Hero section
6. Feature component (the custom treatment — not a default card grid)
7. Testimonial / Social proof
8. Pricing (if applicable)
9. Footer
10. Alert / Toast notifications

**Output**: Design system specification and CSS/JS component definitions

---

## STEP 8 — LAYOUT COMPOSITION

Design the layout for each priority page:

```
PAGE LAYOUT DESIGN
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
Page: [Page name]

Grid: [12-column desktop, 4-column mobile, Xpx gutter]
Container max-width: [1280px or specific]
Side padding: [Mobile: 16px / Desktop: 48px]

SECTION BREAKDOWN:
1. [Section name]: [Purpose] [Component composition]
2. [Section name]: [Purpose] [Component composition]
...

VISUAL HIERARCHY:
Primary attention: [Section/element]
Secondary attention: [Section/element]
CTA position: [Where the primary action appears]
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
```

**Anti-slop check**: Is this layout genuinely designed for this content, or is it the generic SaaS/portfolio/agency template?

**Output**: Layout composition for each priority page

---

## STEP 9 — COMPONENT ARCHITECTURE

**Reference**: `references/12-web-experience.md` (Part 1 — point 8)

For React/Next.js projects, establish the component structure:

```
src/
├── components/
│   ├── ui/              ← Atomic components
│   │   ├── Button.tsx
│   │   ├── Input.tsx
│   │   └── Badge.tsx
│   ├── layout/          ← Layout components
│   │   ├── Navbar.tsx
│   │   ├── Footer.tsx
│   │   └── Container.tsx
│   ├── sections/        ← Page section components
│   │   ├── Hero.tsx
│   │   ├── Features.tsx
│   │   └── Pricing.tsx
│   └── [domain]/       ← Feature-specific components
├── pages/ (or app/)     ← Next.js routing
├── lib/                 ← Utilities, API calls
├── styles/              ← Global CSS, design tokens
└── public/              ← Static assets
```

**Output**: Component architecture document and directory structure

---

## STEP 10 — INTERACTION DESIGN

**Reference**: `references/12-web-experience.md` (Part 2 — Interaction Design)

Specify all interactive states and behaviors:

```
INTERACTION SPECIFICATION
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
HOVER STATES:
  Primary button: [scale(1.02), shadow increase, color shift]
  Navigation links: [underline slide in / color shift]
  Cards: [shadow increase, slight lift, border highlight]
  
FOCUS STATES:
  All interactive elements: [2px offset ring, brand color]
  
SCROLL INTERACTIONS:
  Navigation: [Becomes solid background at 80px scroll]
  Hero elements: [Fade in on load, no scroll-triggered animation]
  
MICRO-INTERACTIONS:
  Form submit button: [Loading spinner on submit]
  Form error: [Shake animation + inline error message]
  Success state: [Checkmark animation + success message]

PAGE TRANSITIONS (if Next.js):
  Route change: [Fade transition, 150ms exit, 200ms enter]
  
MOTION PHILOSOPHY:
  Duration: [Short: 150ms / Medium: 250ms / Long: 400ms]
  Easing: [ease-out for enters, ease-in for exits]
  Reduced motion: [Respects prefers-reduced-motion — animations disabled]
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
```

**Output**: Interaction specification

---

## STEP 11 — STACK SELECTION & JUSTIFICATION

**Reference**: `references/12-web-experience.md` (Part 3), `references/15-technical-standards.md` (WEB TECHNICAL)

```
STACK DECISION
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
Framework:    [HTML+CSS+JS / React / Next.js]
Rationale:    [Why this framework for this project]
Styling:      [Tailwind CSS / CSS Modules / Styled Components]
Animation:    [CSS transitions only / Framer Motion / GSAP]
State:        [None / React hooks / Zustand]
Icons:        [Lucide React / Heroicons / Custom SVG]
Images:       [Next/Image / HTML img with srcset / Cloudinary]
Hosting:      [Vercel / Netlify / GitHub Pages / Custom]
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
```

**Output**: Stack decision with rationale

---

## STEP 12 — IMPLEMENTATION

Produce complete, working code for the deliverable scope.

**Code quality standards**:
- Semantic HTML (`<button>` for buttons, `<a>` for links, landmark elements)
- Proper TypeScript types (no `any`)
- Accessible by default (labels, alt text, ARIA where needed)
- Responsive mobile-first
- Performance-conscious (lazy loading images, code splitting)
- Security-conscious (no XSS vectors, CSP-compatible)
- Clean, readable code with no unnecessary complexity

**Minimum deliverable for each project type**:
- Landing page: Complete HTML/CSS/JS or React implementation
- Marketing site: Home page + 1 key secondary page + components
- Web app: Core layout + primary view + key components

**Output**: Complete, working code

---

## STEP 13 — RESPONSIVE IMPLEMENTATION

**Reference**: `references/15-technical-standards.md` (Responsive Breakpoints)

For every component and page section, verify:
- Mobile (375px): Works first — layout designed for mobile
- Tablet (768px): Appropriate layout adaptation
- Desktop (1280px): Full design realized

```css
/* Mobile-first implementation pattern */
.component {
  /* Mobile base styles */
  display: flex;
  flex-direction: column;
  padding: var(--space-4);
}

@media (min-width: 768px) {
  .component {
    flex-direction: row;
    padding: var(--space-6);
  }
}

@media (min-width: 1280px) {
  .component {
    padding: var(--space-8);
    max-width: 1280px;
    margin: 0 auto;
  }
}
```

**Output**: Verified responsive implementation

---

## STEP 14 — ACCESSIBILITY IMPLEMENTATION

**Reference**: `references/16-accessibility-and-safety.md` (Part 1)

**Accessibility checklist** (implemented, not just checked):
- [ ] Skip to main content link
- [ ] Landmark regions present
- [ ] Heading hierarchy correct
- [ ] All images have alt text
- [ ] All form inputs have labels
- [ ] Focus states visible
- [ ] Color contrast passes (verify with tool)
- [ ] Keyboard navigation works
- [ ] `prefers-reduced-motion` respected
- [ ] Error messages associated with inputs

**Output**: Accessible implementation

---

## STEP 15 — PERFORMANCE OPTIMIZATION

**Reference**: `references/15-technical-standards.md` (WEB TECHNICAL — Performance Budgets)

Optimize for Core Web Vitals:
- **LCP**: Hero image preloaded, largest element renders quickly
- **CLS**: Image dimensions specified, no content shift on load
- **INP**: Interactive elements respond within 200ms
- **Bundle**: Unused dependencies removed, code split by route

```html
<!-- LCP optimization: preload hero image -->
<link rel="preload" as="image" href="hero.webp">

<!-- Images: specify dimensions to prevent CLS -->
<img 
  src="feature.webp" 
  width="800" 
  height="600" 
  loading="lazy"
  alt="[Descriptive alt text]"
>
```

**Output**: Performance-optimized implementation

---

## STEP 16 — SECURITY IMPLEMENTATION

**Reference**: `references/16-accessibility-and-safety.md` (Part 7)

Implement security baseline:
- No `innerHTML` with user content
- Form validation (client + server)
- HTTPS references only
- CSP-compatible (no inline event handlers)
- Input sanitization

**Output**: Security-verified implementation

---

## STEP 17 — BROWSER TESTING

**Reference**: `references/15-technical-standards.md` (Browser Compatibility)

Test checklist:
- [ ] Chrome (latest)
- [ ] Firefox (latest)
- [ ] Safari (latest — most likely to have differences)
- [ ] Edge (latest)
- [ ] Mobile Safari (iPhone)
- [ ] Chrome Android

**Common Safari differences to verify**:
- CSS Grid support
- Flexbox gap property
- Scroll behavior
- Input appearance
- Font rendering

**Output**: Browser compatibility verified

---

## STEP 18 — ANTI-SLOP GATE

**Reference**: `references/13-anti-slop-quality-gates.md` (Website section)

Run website-specific slop detection:
- Generic SaaS template structure?
- Default gradient hero?
- Identical feature cards for all features?
- Generic team section with no creative treatment?
- Animation for the sake of animation?
- Mobile layout that is just stacked desktop layout?

Run the Originality Test:
- [ ] This site looks distinctly different from the top 10 competitors
- [ ] The design language is specific to this brand's personality
- [ ] There is at least one visual decision that required creative thinking

**Output**: Anti-slop report

---

## STEP 19 — QUALITY SCORING

**Reference**: `evals/22-quality-evaluation.md`

Score the web deliverable with website-specific evaluation criteria. Apply extra weight to:
- Functionality (does it actually work?)
- Accessibility (does it meet WCAG 2.1 AA?)
- Performance (does it meet Core Web Vitals targets?)
- Mobile experience (is mobile genuinely well-designed, not just responsive?)

---

## STEP 20 — DEPLOYMENT CHECKLIST

```
DEPLOYMENT CHECKLIST
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
Pre-deployment:
[ ] All page content is real (no Lorem ipsum)
[ ] All images are optimized
[ ] All links work
[ ] Forms submit correctly and have confirmation
[ ] 404 page exists and is designed
[ ] Favicon set
[ ] Open Graph meta tags set
[ ] Robots.txt configured
[ ] Sitemap.xml generated

Performance:
[ ] Lighthouse score > 90 on all metrics
[ ] No console errors
[ ] No network errors (all assets load)

Accessibility:
[ ] WAVE tool shows no errors
[ ] Manual keyboard test passed
[ ] Screen reader spot check passed

Security:
[ ] HTTPS configured
[ ] Security headers set
[ ] No sensitive data in client-side code
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
```

---

## STEP 21 — FINAL DELIVERY PACKAGE

```
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
EXPERIENCE BEAST — FINAL DELIVERY
[Project Name]
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

CREATIVE DIRECTION: [Summary of visual identity concept]
DISTINCTIVE DESIGN DECISION: [What makes this site original]

DELIVERABLES:
[ ] Visual Identity System (tokens, typography, colors)
[ ] Component Library (all specified components)
[ ] Page Implementations: [List pages]
[ ] Interaction Specifications
[ ] Responsive implementation (mobile + tablet + desktop)

TECHNICAL:
Stack:          [Framework / Styling / Animation]
Hosting:        [Recommended hosting]
Bundle Size:    [Estimated]
LCP Target:     [< 2.5s]
Accessibility:  [WCAG 2.1 AA compliant]

NEXT STEPS:
[ ] Content: Real copy and images needed
[ ] Integration: [CMS / Forms / Analytics]
[ ] Launch: Deployment checklist above

QUALITY SCORE: [X]/100 — [LEVEL]
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
```
