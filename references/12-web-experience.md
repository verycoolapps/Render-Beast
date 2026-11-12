# RENDER BEAST — Web Experience Methodology
# EXPERIENCE BEAST Complete Reference

---

## OVERVIEW

EXPERIENCE BEAST treats every web project as a digital product creation exercise, not a code writing exercise. It begins with positioning, audience, and concept — establishing a distinct visual identity before writing a single line of code.

The fundamental rule: **A website must not merely look beautiful in a screenshot. It must function as a complete digital experience.**

---

## SUPPORTED WEB CATEGORIES

- Landing pages (product, SaaS, campaign, waitlist)
- Corporate websites
- Portfolio websites (personal, agency, studio)
- SaaS platform interfaces
- Dashboard and analytics interfaces
- E-commerce (product listings, product detail, cart, checkout)
- Editorial websites and digital publications
- Interactive storytelling experiences
- Web applications
- Product showcase sites
- Immersive marketing experiences
- Experimental and artistic interfaces
- Documentation sites
- Event websites

---

## PART 1 — DESIGN ARCHITECTURE (10-PART FRAMEWORK)

### 1. PRODUCT POSITIONING

Before visual decisions, establish:
- What is this, fundamentally? (The clearest possible description)
- Who is it for? (Specific, not "everyone")
- Why would they choose this over alternatives?
- What is the single most important thing to communicate?
- What action must the visitor take?

### 2. TARGET AUDIENCE

Define with precision:
- Demographics (age range, profession, income, geography)
- Psychographics (values, aspirations, fears, desires)
- Technical sophistication (affects complexity of interface language)
- Relationship to the category (new vs. experienced vs. expert)
- Device usage patterns (primarily mobile vs. desktop vs. mixed)
- Attention span in this context (what is their intent when visiting?)

### 3. INFORMATION ARCHITECTURE

Structure the content hierarchy:
- What is the most important piece of information?
- What is the second most important?
- What information supports each of those?
- What information must be accessible but need not be primary?
- What information belongs in a secondary page?

Build the IA as a tree, then validate against user journeys.

### 4. USER JOURNEYS

Map the primary paths through the site:
- Primary journey (most common visitor goal)
- Secondary journey (second most common)
- Conversion journey (the path to the most important action)
- Error/edge case journeys (what happens when something goes wrong?)

Each journey has: entry point → actions → decision points → destination.

### 5. SITEMAP

Define the page structure:
```
HOME
├── ABOUT
│   ├── Team
│   └── Story
├── PRODUCT / SERVICES
│   ├── Feature Detail 1
│   └── Feature Detail 2
├── PRICING
├── CASE STUDIES / WORK
│   └── Case Study Detail
├── BLOG
│   └── Article
├── CONTACT
└── LEGAL
    ├── Privacy Policy
    └── Terms
```

Prune ruthlessly. Every page must justify its existence.

### 6. CONTENT STRATEGY

For each page, define:
- Primary message (what the page communicates)
- Supporting messages
- Content types needed (copy, images, video, data, testimonials)
- Call to action
- SEO target (keyword + search intent)
- Content length guidance

### 7. VISUAL IDENTITY

Establish the complete visual language:
- Typography system (typeface selection, scale, hierarchy)
- Color system (palette, semantic colors, usage rules)
- Spacing system (base unit, scale)
- Border and radius style
- Shadow system
- Icon style
- Illustration style (if applicable)
- Photography direction

### 8. DESIGN SYSTEM

Define the token layer:
```css
/* Typography Scale */
--text-xs: 0.75rem;    /* 12px */
--text-sm: 0.875rem;   /* 14px */
--text-base: 1rem;     /* 16px */
--text-lg: 1.125rem;   /* 18px */
--text-xl: 1.25rem;    /* 20px */
--text-2xl: 1.5rem;    /* 24px */
--text-3xl: 1.875rem;  /* 30px */
--text-4xl: 2.25rem;   /* 36px */
--text-5xl: 3rem;      /* 48px */
--text-6xl: 3.75rem;   /* 60px */
--text-7xl: 4.5rem;    /* 72px */

/* Spacing Scale (base: 4px) */
--space-1: 0.25rem;    /* 4px */
--space-2: 0.5rem;     /* 8px */
--space-3: 0.75rem;    /* 12px */
--space-4: 1rem;       /* 16px */
--space-6: 1.5rem;     /* 24px */
--space-8: 2rem;       /* 32px */
--space-12: 3rem;      /* 48px */
--space-16: 4rem;      /* 64px */
--space-24: 6rem;      /* 96px */
--space-32: 8rem;      /* 128px */

/* Semantic Colors */
--color-primary: [brand primary];
--color-primary-hover: [darker shade];
--color-secondary: [brand secondary];
--color-background: [page background];
--color-surface: [card/element background];
--color-border: [default border];
--color-text-primary: [main text];
--color-text-secondary: [supporting text];
--color-text-muted: [placeholder/disabled];
--color-success: [success states];
--color-warning: [warning states];
--color-error: [error states];
--color-info: [info states];
```

### 9. COMPONENT ARCHITECTURE

Define the component hierarchy:
- **Tokens** — Design decisions as variables (colors, typography, spacing)
- **Atoms** — Smallest components (Button, Input, Badge, Icon)
- **Molecules** — Composed atoms (FormField, SearchBar, NavItem)
- **Organisms** — Composed molecules (Navbar, HeroSection, PricingCard)
- **Templates** — Page layout structures
- **Pages** — Template instances with real content

### 10. RESPONSIVE BEHAVIOR

Define behavior at each breakpoint:
- Mobile (375px): Single column, touch-first, thumb-zone navigation
- Tablet (768px): Flexible columns, expanded navigation options
- Desktop (1280px): Multi-column, hover states active, full navigation
- Large Desktop (1440px+): Fixed max-width with generous margins

---

## PART 2 — VISUAL DESIGN DEEP-DIVE

### Layout Composition

**Grid Systems**
- 4-column grid for mobile
- 8-column grid for tablet
- 12-column grid for desktop
- Define gutter width at each breakpoint
- Define container max-width (typically 1200-1440px)
- Define container side padding (16px mobile, 24px tablet, 48px+ desktop)

**Visual Hierarchy in Layout**
- Primary content: Most visual weight, prominent position
- Secondary content: Reduced contrast, subordinate position
- Supporting content: Small, low contrast, footnote position
- CTAs: Visually distinct, strategically placed

**Whitespace Strategy**
- Generous whitespace signals confidence and premium quality
- Tight whitespace signals density and information richness
- Never fill space for the sake of filling it

### Interaction Design

**Hover States**
- Every interactive element must have a visible hover state
- Transitions: 150-200ms ease-out for simple states, 250-300ms for complex
- Color shift, shadow addition, or subtle transform (translateY(-2px) for buttons)
- Never abrupt state changes without transition

**Focus States**
- Required for keyboard accessibility
- 2px offset, high-contrast focus ring (outline or box-shadow)
- Match the brand's color system
- Never remove outline without providing an alternative

**Active States**
- Pressed state for buttons: scale(0.98) or slight position shift
- Duration: 100ms — faster than hover

**Scroll Interactions**
- Parallax: Use sparingly, never for primary content
- Fade-in on scroll: Maximum 60fps via IntersectionObserver, not scroll events
- Sticky navigation: Include visible state transition when sticking activates
- Scroll progress: Only when genuinely informative

**Micro-interactions**
- Form validation: Inline, immediate feedback
- Loading states: Progress indication within 100ms of action
- Success/error feedback: Clear, positioned near the action trigger
- Toggle switches: Animated state transition
- Accordion/expand: Smooth height animation via CSS max-height or JS

**Page Transitions**
- Shared element transitions between pages (Framer Motion, View Transitions API)
- Exit animation: 150ms max (users do not wait for pages to leave)
- Enter animation: 200-400ms, element-staggered where appropriate

### Empty States, Loading States, Error States

Every component that loads or modifies data must have all three:

**Loading State**: Skeleton screens (not spinners for content loading)
**Empty State**: Clear illustration/icon + message + action
**Error State**: Clear description of what went wrong + recovery action

---

## PART 3 — TECHNICAL IMPLEMENTATION

### Stack Selection Framework

**Use plain HTML/CSS/JS when:**
- Simple marketing page with minimal interactivity
- Extreme performance requirements
- No dynamic data
- Maximum browser compatibility needed

**Use React when:**
- Complex interactive UI
- Shared state across components
- Rich component library needed
- Team familiarity with React

**Use Next.js when:**
- SEO-critical pages
- Server-side data needed
- API routes needed
- File-based routing desired
- Production deployment to Vercel

**Use TypeScript always for:**
- Any project beyond a one-day prototype
- Component prop safety
- API response type safety

**Use Tailwind CSS when:**
- Rapid development needed
- Design token consistency important
- Team comfortable with utility-first

**Use Framer Motion for:**
- Complex animations
- Shared element transitions
- Gesture-based interactions
- Scroll-linked animations

**Use GSAP for:**
- Timeline-based animations
- Complex sequenced animations
- ScrollTrigger advanced effects
- When Framer Motion cannot achieve the effect

**Use Three.js / React Three Fiber when:**
- 3D product visualization
- WebGL-based creative effects
- Immersive experiences
- When CSS cannot achieve the visual

### Production-Quality HTML Template

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <meta name="description" content="[Page description — 150-160 characters]">
  
  <!-- Open Graph -->
  <meta property="og:title" content="[Page title]">
  <meta property="og:description" content="[OG description]">
  <meta property="og:image" content="[OG image URL]">
  <meta property="og:type" content="website">
  
  <!-- Twitter Card -->
  <meta name="twitter:card" content="summary_large_image">
  
  <!-- Security Headers (also set server-side) -->
  <meta http-equiv="X-Content-Type-Options" content="nosniff">
  
  <!-- Fonts (from approved CDN or self-hosted) -->
  <link rel="preconnect" href="https://fonts.googleapis.com">
  <link rel="preload" as="style" href="[font URL]">
  
  <!-- Canonical -->
  <link rel="canonical" href="[page URL]">
  
  <!-- Favicon -->
  <link rel="icon" href="/favicon.ico" sizes="any">
  <link rel="icon" href="/favicon.svg" type="image/svg+xml">
  <link rel="apple-touch-icon" href="/apple-touch-icon.png">
  
  <title>[Page Title | Brand Name]</title>
</head>
<body>
  <!-- Skip to main content (accessibility) -->
  <a href="#main-content" class="skip-link">Skip to main content</a>
  
  <header role="banner">
    <nav aria-label="Main navigation">
      <!-- Navigation -->
    </nav>
  </header>
  
  <main id="main-content" role="main">
    <!-- Page content -->
  </main>
  
  <footer role="contentinfo">
    <!-- Footer -->
  </footer>
</body>
</html>
```

---

## PART 4 — WEBSITE QUALITY CHECKLIST

### Responsive
- [ ] Mobile (375px): Layout works, text readable, touch targets ≥44px
- [ ] Tablet (768px): Layout adapts appropriately
- [ ] Desktop (1280px): Full layout, hover states active
- [ ] No horizontal scroll at any breakpoint

### Semantic HTML
- [ ] Only one `<h1>` per page
- [ ] Heading hierarchy is logical (h1 → h2 → h3)
- [ ] `<main>`, `<header>`, `<footer>`, `<nav>` landmarks present
- [ ] `<button>` for actions, `<a>` for navigation
- [ ] Form elements properly labeled

### Accessibility
- [ ] All images have descriptive `alt` text (or `alt=""` for decorative)
- [ ] Color is not the only way information is conveyed
- [ ] Focus states visible for all interactive elements
- [ ] Keyboard navigation works throughout
- [ ] Screen reader test: logical content order
- [ ] Motion respects `prefers-reduced-motion`
- [ ] Color contrast ≥ 4.5:1 for normal text, 3:1 for large text

### Performance
- [ ] Largest Contentful Paint < 2.5s
- [ ] Cumulative Layout Shift < 0.1
- [ ] Images are optimized (WebP, appropriate size)
- [ ] No render-blocking resources
- [ ] JavaScript bundle < 150KB gzipped initial
- [ ] Fonts: subset, preloaded, `font-display: swap`

### Security
- [ ] HTTPS
- [ ] Content Security Policy header set
- [ ] No inline event handlers (onclick="...") in production
- [ ] Form inputs sanitized
- [ ] Third-party scripts audited

---

## EXPERIENCE BEAST QUALITY RULES

Strictly prohibited:

- Generic hero section (gradient background + headline + card row)
- Same navigation pattern as 90% of SaaS websites without creative justification
- Features grid with identical card structure for all features
- Testimonials section without visual differentiation
- Pricing table with identical structure across all tiers
- Footer as an afterthought (footers communicate trust and completeness)
- Interactive elements with no visible hover or focus states
- Form fields without labels (placeholder text does not count as a label)
- Color combinations that fail contrast requirements
- "Coming soon" or "placeholder text" in final deliverables
- Fake user data or fake testimonials
- Animations that run without respect for `prefers-reduced-motion`
- JavaScript-dependent content that breaks without JS
- Mobile layout that is merely a stacked version of the desktop layout (design for mobile, adapt up)
