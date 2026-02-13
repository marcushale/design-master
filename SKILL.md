---
name: design-master
description: |
  Comprehensive design skill: philosophy, principles, anti-patterns, pipeline, and implementation.
  
  USE WHEN:
  - Building ANY user interface (web, mobile, dashboard, landing page)
  - Need design system guidance (colors, typography, spacing, layout)
  - Want to avoid generic "AI slop" aesthetics
  - Designing for Apple platforms (iOS/macOS/watchOS)
  - Accessibility/WCAG compliance questions
  - Data-heavy interfaces (tables, filters, bulk actions)
  - Design system governance and handoff QA
  - Reviewing or critiquing existing designs
  
  COVERS: Philosophy, anti-AI aesthetic, design pipeline, tokens & foundations, components, data-heavy patterns, animation, accessibility (WCAG 2.2), mobile & touch, platform-specific (Apple HIG, web), design system governance, handoff QA, and implementation checklists.
  
  OUTPUT: Intentional, distinctive, human-crafted interfaces with systematic consistency.
---

# Design Master

The unified design skill. Philosophy → Pipeline → Foundations → Components → Patterns → Governance → QA.

---

## Part 1: Philosophy

### Core Truths

1. **Intentionality Over Defaults** — Every pixel exists because you made a choice. AI averages; humans distinctify.
2. **Clarity Over Cleverness** — Hierarchy is obvious. Actions are predictable. Feedback is immediate.
3. **Consistency Breeds Familiarity** — Patterns repeat. Terminology is uniform. Platform conventions respected.
4. **Accessibility is Non-Negotiable** — Works for everyone. Keyboard navigable. Screen reader friendly.

### The Human-Crafted Aesthetic

| Feature | ❌ AI/Generic | ✅ Human/Crafted |
|---------|--------------|------------------|
| **Color** | Hyper-saturated, glossy gradients | Muted, semantic, system-based |
| **Motion** | Linear transitions, slow fades | Spring physics, snappy (100-200ms) |
| **Content** | "We're changing the world" | "Here's how this solves your problem" |
| **Density** | Excessive whitespace | High information density for experts |
| **Details** | Generic stock illustrations | Custom elements, intentional texture |

**Gold Standards:** Linear, Raycast, Vercel — tools for mastery, not generic friendliness.

---

## Part 2: The Design Pipeline

```
CONTEXT → DESIGN → BUILD → REVIEW → FIX → VALIDATE
```

### The Multi-Model Quality Loop (MANDATORY)

**For ANY user-facing work, you MUST use a create-review-fix cycle:**

```
1. CREATE (Opus/Sonnet) — Generate initial implementation
2. REVIEW (Codex/Gemini) — Fresh eyes critique with Structural Consistency Checklist
3. FIX (Opus/Sonnet) — Address ALL findings before shipping
4. VALIDATE — Run the Four Tests + Structural Consistency Check
```

**Review Prompt Template:**
```
Review this implementation against these structural rules:
1. Button contrast: Light text on colored backgrounds?
2. Icons: SVG icons only, no native emoji?
3. Alignment: All elements in centered sections actually centered?
4. Section rhythm: Alternating backgrounds create visual hierarchy?
5. Container consistency: All sections respect same max-width?
6. Visual flow: Can you distinguish where sections start/end?

Also check: gaps, anti-patterns, edge cases, accessibility issues, missing states.
```

**Why Mandatory:**
- Builder blindness is real — you won't see your own mistakes
- Different models catch different issues
- Structural bugs (alignment, containment) are invisible to the creator
- Catches "works for me" assumptions before users see them

**No exceptions.** Even "simple" landing pages need review.

### Phase 1: CONTEXT

**Problem Definition** — Before pixels:
- What problem are we solving?
- Who has this problem? (Be specific)
- How do they currently solve it?
- What does success look like?

**Intent Statement** — Write first:
```
WHO: [Target user — specific]
WHAT: [What they accomplish]
FEEL: [ONE word]
ANTI: [3 patterns to reject]
```

---

## Single Page Track (Landing Pages, Marketing Sites)

For simple single-page sites, use this streamlined checklist instead of the full pipeline:

### Quick Setup
```yaml
INTENT:
  who: [target user]
  goal: [primary conversion action]
  feel: [one word]

TOKENS:
  background: [page base]
  surface: [cards/sections - MUST differ from background]
  foreground: [text]
  accent: [CTAs]
  
SECTIONS: [list sections in order]
```

### Structural Consistency Checklist (MANDATORY)

Before shipping ANY single-page site, verify ALL of these:

**Container Consistency:**
- [ ] Define ONE `max-width` for content (1200-1440px)
- [ ] ALL sections use the same container width
- [ ] Full-bleed sections only for intentional background color, content still in container
- [ ] No section breaks the horizontal bounds unexpectedly

**Visual Rhythm:**
- [ ] Sections alternate between at least 2 background colors
- [ ] Header is visually distinct from first section
- [ ] Footer is visually distinct from last section
- [ ] Eye can clearly identify where each section starts/ends

**Alignment Integrity:**
- [ ] If a section is centered, ALL elements in it are centered (including small helper text)
- [ ] If left-aligned, consistently left-aligned
- [ ] No orphaned alignment (e.g., centered heading with left-aligned subtext)

**Button/CTA Contrast:**
- [ ] Filled buttons: Light text on colored background (white on accent)
- [ ] Never dark text on medium/dark colored backgrounds
- [ ] Contrast ratio meets 4.5:1 for button text
- [ ] Nav buttons use SAME styling as content buttons (no inheritance bugs)

**Hero Impact:**
- [ ] Hero headline is outsized (larger than other H1s on page)
- [ ] Hero has generous vertical padding (min 6rem top/bottom)
- [ ] Hero creates immediate visual impact when page loads

**Icons (CRITICAL):**
- [ ] NEVER use native emoji (💭🤝🌱) — they look amateur and render inconsistently
- [ ] Always use SVG icons (Lucide, Heroicons, Phosphor, or custom)
- [ ] Icons should be monochrome and match the design system
- [ ] If you don't have icons, use NO icons — blank is better than emoji

**Typography Hierarchy:**
- [ ] One display font for headings
- [ ] One body font for text
- [ ] Clear size distinction between H1 > H2 > H3 > body

**Footer Minimalism:**
- [ ] Single row layout (logo left, links right)
- [ ] No section headers ("LINKS", "FOLLOW US") — just show them
- [ ] Copyright inline with links, not separate row
- [ ] Remove taglines/descriptions if not needed

### Visual Interest & Texture (CRITICAL)

Clean design is good. **Too clean is sterile.** Every site needs visual character.

**The Problem:**
Sites that are structurally correct but feel "undesigned" — all flat colors, no photography, no texture, no visual moments. They're correct but forgettable.

**IMPORTANT: These are STARTING POINTS, not a menu.** Don't just pick one and execute it literally. Use these as inspiration to create something UNIQUE to your specific product. The best designs combine elements, subvert expectations, or invent entirely new approaches based on the brand's personality.

**The goal: Every site should feel like it could ONLY exist for this specific product.**

---

**APPROACH A: Photography-Forward**
Bold, full-bleed images. Let photos do the heavy lifting.
- Hero: Full-screen background image with text overlay
- Section breaks: Photo strips or editorial image grids
- Cards: Image-first with text below
- **Color limit: 3 max** — Background, text, one accent. Photos provide the color.
- *Starting point for:* Lifestyle, travel, food, fashion, real estate
- *Twist it:* Duotone photos, masked shapes, mixed with illustration

**APPROACH B: Playful Physics & Sketch**
Hand-drawn meets interactive physics. Think "Crayon Physics Deluxe" — fun and tactile but NOT childish.
- Hero: Hand-drawn sketchy elements with physics-based interactions
- Lines: Pencil strokes, chalk textures, blueprint-style annotations
- Motion: Elements that bounce, swing, stack — real physics simulation
- Palette: Craft paper backgrounds, muted crayons, chalkboard aesthetics
- Details: Scribbled annotations, crossed-out text, "work in progress" feel
- **Color limit: 4-5 max** — Paper/chalk background + 2-3 muted crayon colors. NO saturated primaries.
- *Starting point for:* Creative tools, indie games, educational, maker brands
- *Key tension:* Playful execution + serious/smart content = sophisticated fun
- *Twist it:* Combine with engineering diagrams, architectural sketches, or notebook margins

**APPROACH C: Bold Typography & Color**
Type IS the visual. Massive, expressive, confident.
- Hero: Oversized display type (150px+), maybe animated
- Color blocking: Sections in bold contrasting colors
- Minimal imagery — let the words speak
- **Color limit: 2-3 max** — Bold, high-contrast. One dominant, one accent, optional neutral.
- *Starting point for:* Agencies, portfolios, statements, manifestos
- *Twist it:* Variable fonts, kinetic type, mixed weights/styles

**APPROACH D: Texture & Material**
Tactile, physical feeling. Paper, grain, depth.
- Backgrounds: Paper textures, gradients, grain overlays
- Shadows: Realistic drop shadows, layered elements
- Details: Subtle noise, halftone patterns, embossed effects
- **Color limit: 3-4 max** — Monochromatic or analogous. Texture provides variety, not color.
- *Starting point for:* Luxury, craft, artisan, print-inspired
- *Twist it:* Brutalist textures, industrial materials, unexpected surfaces

**APPROACH E: Code & Engineering Animation**
Technical precision as visual interest. Like Stripe's touchable pincushion needles — interactive, precise, mesmerizing.
- Hero: Interactive canvas elements (WebGL, Three.js, or CSS) that respond to cursor/scroll
- Aesthetic: Dark mode, monospace type, terminal greens, engineering blueprints
- Motion: Procedural, code-driven animations — NOT flashy neon or "AI purple"
- Interactions: Hover reveals data, click triggers calculations, elements connect with lines
- Details: Grid overlays, coordinate markers, performance metrics
- **Color limit: 2 max** — Dark background + ONE accent color (teal, green, or blue). Monochromatic is key.
- *Starting point for:* Developer tools, APIs, infrastructure, fintech, data products
- *Anti-pattern:* Neon colors, purple gradients, particle explosions — these scream "AI generated"
- *Reference:* Stripe's homepage (pincushion, gradient mesh), Linear, Vercel
- *Key principle:* Motion should feel ENGINEERED, not decorative — like watching code execute
- *Twist it:* Data visualization as hero, live API responses, generative art from algorithms

**APPROACH F: Editorial & Grid**
Magazine-style asymmetry. Intentional tension.
- Layout: Broken grids, overlapping elements, varied columns
- Images: Mixed sizes, some bleed off edges
- Typography: Pull quotes, varied sizes, margin notes
- **Color limit: 3-4 max** — Sophisticated palette. One accent (often red), rest neutral.
- *Starting point for:* Publications, blogs, cultural, journalism
- *CRITICAL:* Must collapse gracefully on mobile — complex grids become single column, margin labels become inline, all content stays within viewport
- *Twist it:* Newspaper style, zine aesthetic, mixed media collage

---

**Creating Your Own Approach:**

The best designs don't fit neatly into categories. To create something truly unique:

1. **Start with the product's world** — What materials, textures, colors exist in this domain?
2. **Find unexpected references** — Look outside web design. Architecture, fashion, print, nature.
3. **Identify a signature element** — What ONE thing could only exist for THIS product?
4. **Combine influences** — Photography + bold type? Editorial + motion? Texture + illustration?
5. **Break a rule intentionally** — What convention can you subvert that reinforces the brand?

**Examples of hybrid/custom approaches:**
- Linear: Dark UI + subtle gradients + micro-animations + engineering precision
- Notion: Illustration + playful type + generous whitespace + tool-like simplicity
- Stripe: Gradients + bold statements + interactive demos + technical credibility

---

**Anti-Pattern: The Timid Overlay**
❌ Adding a 5% opacity photo behind text and calling it "visual interest"
❌ Applying the same subtle treatment to every site
❌ Textures so faint they're invisible
❌ Picking an approach and executing it literally without customization

**The Test:** Would a non-designer notice the visual character? If they'd say "it's just a white page with text" → you haven't added enough.

**Photo Resources (Free for Commercial Use):**
| Source | Best For | License |
|--------|----------|---------|
| Unsplash | General, lifestyle | Free |
| Pexels | General, diverse | Free |
| Pixabay | Illustrations, vectors | Free |
| Burst (Shopify) | E-commerce, business | Free |

---

### Phase 2: DESIGN

**Information Architecture (Complex Products):**
1. **Content Inventory** — What content/features exist?
2. **User Flows** — Key paths users take (signup, purchase, core task)
3. **Sitemap** — Page hierarchy and navigation structure
4. **Wireframes** — Low-fidelity layout before visual design

**Domain Exploration (New Products):**
1. **Domain** — 5+ concepts/metaphors from this product's world
2. **Color World** — Colors that exist naturally in this domain
3. **Signature** — One element that could ONLY exist for this product
4. **Defaults to Reject** — 3 obvious patterns to avoid

**Token Definition** — All values require rationale (WHY?):
```yaml
DIRECTION:
  personality: [e.g., "Precision & Density"]
  depth_strategy: [borders-only | subtle-shadows | layered]

PALETTE: background, surface, foreground, muted, accent, border
TYPOGRAPHY: display, body, mono + scale
SPACING: base unit (4px or 8px) + scale
```

Design Tokens = CSS Variables. Define once, use everywhere.

### Phase 3: REVIEW (Optional)

For landing pages/new UIs: Generate 2-3 variations, get approval before heavy build.
Skip: Bug fixes, established systems, internal tools.

### Phase 3: BUILD

- CSS Variables for all tokens (semantic names like `--surface-elevated`)
- Component isolation (no global overrides)
- 100-200ms transitions, ease-out
- All states: hover, active, disabled, focus, loading

### Phase 4: REVIEW

**For significant work, get a fresh review:**
- Spawn a different model (Codex, Gemini Pro) to critique
- Review prompt: "Critique this implementation for gaps, anti-patterns, edge cases, accessibility issues, and missing states"
- Document findings before fixing

### Phase 5: FIX

Address review findings systematically:
- Group by severity (critical → nice-to-have)
- Fix all critical/high issues
- Document decisions on deferred items

### Phase 6: VALIDATE

**The Four Tests:**
1. **Swap Test** — Would defaults feel different? (YES required)
2. **Squint Test** — Hierarchy visible? (YES required)
3. **Signature Test** — 5 intentional choices identifiable?
4. **Token Test** — Variables sound like this product?

### Phase 7: PRE-DEPLOY QA (MANDATORY)

**⚠️ DO NOT SKIP THIS.** Every deploy must pass these checks.

**Desktop Verification (5 min):**
1. Open site in browser at 1440px width
2. Scroll entire page — check section spacing, alignment, visual rhythm
3. Click every navigation link — verify they work
4. Click every CTA/button — verify hover states
5. Check footer links

**Mobile Verification (5 min) — CRITICAL:**
1. Open browser DevTools (F12 or Cmd+Option+I)
2. Toggle device toolbar (Cmd+Shift+M or click phone icon)
3. Select "iPhone 12 Pro" or similar (390px width)
4. **Test hamburger menu:**
   - [ ] Hamburger icon visible?
   - [ ] Click → menu opens full-screen?
   - [ ] Click link → menu closes AND navigates?
   - [ ] Click X/hamburger → menu closes?
5. **Scroll test:**
   - [ ] All content visible (nothing cut off)?
   - [ ] Text readable (16px+ body)?
   - [ ] Buttons tappable (44px+ touch targets)?
   - [ ] No horizontal scroll?
6. **Layout collapse:**
   - [ ] Multi-column → single column?
   - [ ] Cards stack vertically?
   - [ ] No overlapping elements?

**Functional Verification (3 min):**
1. Open browser console (Cmd+Option+J)
2. Reload page — check for JavaScript errors (red text)
3. If errors exist → FIX BEFORE DEPLOY
4. Test any interactive elements (forms, animations, toggles)

**Cross-Browser Spot Check (2 min):**
- If you built in Chrome, quick-check in Safari (or vice versa)
- Mobile: Test in both iOS Safari and Chrome if possible

**The "Fresh Eyes" Test:**
Before final deploy, take a 2-minute break. Come back and view the site as if seeing it for the first time. Does anything feel off?

**Deployment Gate:**
```
□ Desktop scroll check passed
□ Mobile hamburger menu works
□ Mobile layout collapses properly  
□ No console errors
□ Cross-browser spot check done
□ Fresh eyes review done

ALL BOXES CHECKED → Deploy
ANY BOX UNCHECKED → Fix first
```

---

## Part 3: Tokens & Foundations

### Color

**Semantic Structure (oklch preferred):**
```css
--background: oklch(0.145 0 0);    /* Page base */
--surface: oklch(0.205 0 0);       /* Cards */
--foreground: oklch(0.985 0 0);    /* Primary text */
--muted: oklch(0.556 0 0);         /* Secondary text */
--accent: oklch(0.649 0.237 267);  /* CTAs */
--border: oklch(0.922 0 0 / 0.15); /* Dividers */
```

**Contrast:** 4.5:1 body text, 3:1 large text/UI.

### Typography

**Fonts:**
- **System:** -apple-system, SF Pro
- **Web:** Inter (with intentional reason), Outfit, DM Sans
- **Display:** Space Grotesk, Instrument Serif
- **Mono:** JetBrains Mono, Geist Mono

**Scale:** 12 → 14 → 16 → 18 → 24 → 32 → 48 → 72

**Rules:** Use `rem` not `px`. Headings: tighter tracking. Data: `tabular-nums`.

### Spacing

**8-Point Grid:** 4, 8, 12, 16, 24, 32, 48, 64, 80, 96

| Size | Use |
|------|-----|
| XS (4px) | Icon + text gaps |
| S (8px) | Related items |
| M (16px) | Standard |
| L (24px) | Section spacing |
| XL+ (32-48px) | Major sections |

### Layout & Grid

- **Container:** max-width 1200-1440px, centered
- **Columns:** 12-column grid, 16-24px gutters
- **Fluid typography:** `clamp(1rem, 0.9rem + 0.5vw, 1.25rem)`
- **Touch targets:** 44×44px minimum

### Depth Strategies (Pick ONE)

**Borders-Only** — Technical, dense:
```css
border: 1px solid rgba(255,255,255,0.1);
```

**Subtle Shadows** — Approachable:
```css
box-shadow: 0 1px 3px rgba(0,0,0,0.1), 0 1px 2px rgba(0,0,0,0.06);
```

**Glassmorphic** — Premium:
```css
background: rgba(255,255,255,0.1);
backdrop-filter: blur(10px);
```

### Dark Mode

- Higher elevation = slightly lighter surface (not shadow)
- Avoid pure black (#000) — use charcoal (#0d0d0d to #1a1a1a)
- Test both modes simultaneously
- Shadows darker/more subtle in dark mode

---

## Part 4: Components

### Buttons

**Hierarchy:** Primary (filled) → Secondary (outlined) → Tertiary (ghost)
**States:** Default → Hover → Active → Disabled → Loading
**Sizes:** 32-36px (small), 40-44px (medium), 48-56px (large)
**Rules:** 44×44px touch target. Action labels ("Save Changes" not "OK").

### Forms

- Labels above fields (never placeholder-as-label)
- Visible focus states (2px ring)
- Inline validation with helpful messages
- Field height: 40-48px

### Cards

- Border radius: 8-12px (modern), 0px (brutalist)
- Padding: 16-24px
- Types: Flat, Elevated, Interactive, Glass

### Navigation

- **Top Nav** — Web, global
- **Bottom Tab Bar** — Mobile (3-5 items)
- **Sidebar** — Desktop complex apps
- **Command Palette** — Power users (`Cmd+K`)

### States

**Loading:** Skeleton screens for content, spinners for actions
**Empty:** Clear messaging + suggested actions
**Error:** Toast for recoverable, inline near problem, full-page for unrecoverable

### Content & Microcopy

**Button Labels:** Action verbs ("Save Changes", "Send Message", not "OK", "Submit")
**Error Messages:** Say what went wrong + how to fix it ("Email already registered. Try logging in instead.")
**Empty States:** Explain why empty + what to do ("No projects yet. Create your first project to get started.")
**Confirmations:** Be specific ("Delete 'Q4 Report'? This cannot be undone." not "Are you sure?")

**Tone:** Match the product personality. Professional tools = direct. Consumer apps = friendly.

### Responsive Patterns

**Layout Transformations:**
- **Stack:** Multi-column → single column on mobile
- **Reflow:** Grid items reduce columns (4 → 2 → 1)
- **Collapse:** Sidebar → hamburger menu
- **Hide:** Secondary actions move to overflow menu
- **Prioritize:** Show most important content first on small screens

**Breakpoint Behavior:**
```
Mobile (<640px): Single column, bottom nav, full-width cards
Tablet (640-1024px): 2 columns, may keep sidebar or hamburger
Desktop (>1024px): Full layout, sidebar visible, multi-column grids
```

**Testing:** Don't just resize browser. Test the "uncomfortable zones" between breakpoints where layouts break.

---

## Part 5: Data-Heavy Interfaces

For expert users managing large datasets. Prioritize density, speed, keyboard efficiency.

### Data Tables

**Core Features:**
- Column configuration (toggle, reorder, resize)
- Multi-column sorting with visual indicators
- Sticky headers (vertical and horizontal for ID column)
- Density toggle (compact/comfortable)

**Selection:**
- Checkbox column with tri-state header (none/all/some)
- Shift+click range selection
- Cross-page selection: "All 50 on page selected. [Select all 1,245]"

**Inline Editing:**
- Click-to-edit cells
- Tab saves + moves right, Enter saves + moves down
- Dirty state indicators (corner triangle)

### Filtering

**Filter Bar:** Global search + attribute filters + active filter chips
**Faceted Search:** Counts per facet, multi-select within (OR), across (AND)
**Saved Views:** Save filter + sort + columns as named presets

### Bulk Actions

**Action Bar:** Appears on selection with count + high-frequency actions
**Confirmation:** Non-destructive = toast + undo. Destructive = modal. Mass destructive = type confirmation phrase.

### Pagination

- **Standard pagination:** For specific records, jumping
- **Infinite scroll:** For discovery (requires virtual scrolling)
- **Load more:** Middle ground, keeps footer
- **Cursor-based:** For real-time/massive data (no "jump to page")

### Keyboard Workflows

- `?` — Show shortcuts
- `Cmd+K` — Command palette
- `j/k` — Navigate rows (Vim-style)
- `e` — Edit, `d` — Delete, `x` — Select
- Focus trap in modals, return focus on close

### Empty States

**Filtered to zero:** "No results for [filters]. Clear all filters."
**System error:** "Failed to load. [Retry]"
**First run:** "No items yet. [Create first]"

---

## Part 6: Animation & Motion

**Durations:**
- Quick: 100-150ms (hover, press)
- Standard: 200-300ms (transitions)
- Slow: 400-500ms (page transitions)

**Easing:** `ease-out` for most, `ease-in` for exits only.

**Micro-interactions:**
```css
button:active { transform: scale(0.98); }
.card:hover { transform: translateY(-2px); }
:focus-visible { outline: 2px solid var(--accent); outline-offset: 2px; }
```

**Rules:**
- Snappy > smooth
- Respect `prefers-reduced-motion`
- No scrolljacking
- No layout shift (CLS)
- Use `transform` and `opacity` only (avoid animating width/height/top/left)
- Add `will-change` only on elements that will animate
- Use `translate3d()` for hardware acceleration
- Use `passive: true` on scroll listeners

### Performance Animation Patterns

**Hardware-Accelerated Transitions:**
```css
.element {
  transition: transform 0.35s cubic-bezier(0.22, 1, 0.36, 1), 
              opacity 0.35s ease, 
              box-shadow 0.35s ease;
  will-change: transform;
}

/* AVOID: */
transition: all 0.3s;  /* Too broad, triggers full repaint */
transition: width 0.3s, height 0.3s;  /* Layout thrashing */
```

**Parallax with RAF:**
```javascript
const parallaxElements = document.querySelectorAll('[data-parallax]');
let rafId = null;

const updateParallax = () => {
  const scrollY = window.scrollY;
  parallaxElements.forEach(el => {
    const speed = Number(el.dataset.parallax) || 0.1;
    el.style.transform = `translate3d(0, ${scrollY * speed * -1}px, 0)`;
  });
  rafId = null;
};

window.addEventListener('scroll', () => {
  if (!rafId) rafId = requestAnimationFrame(updateParallax);
}, { passive: true });
```

**Scroll Reveal with IntersectionObserver:**
```javascript
const revealObserver = new IntersectionObserver((entries) => {
  entries.forEach(entry => {
    if (entry.isIntersecting) {
      entry.target.classList.add('is-visible');
      revealObserver.unobserve(entry.target);
    }
  });
}, { threshold: 0.18, rootMargin: '0px 0px -10% 0px' });

document.querySelectorAll('.reveal').forEach(el => revealObserver.observe(el));
```

---

## Part 7: Accessibility (WCAG 2.2)

### New in WCAG 2.2

| Criterion | Level | Summary |
|-----------|-------|---------|
| 2.4.11 Focus Not Obscured | AA | Focused element not hidden behind sticky elements |
| 2.5.7 Dragging Movements | AA | Single-pointer alternative for drag actions |
| 2.5.8 Target Size (Minimum) | AA | 24×24px minimum or sufficient spacing |
| 3.2.6 Consistent Help | A | Help in same location across pages |
| 3.3.7 Redundant Entry | A | Don't make users re-enter data |
| 3.3.8 Accessible Authentication | AA | Allow paste, support password managers |

### Key Patterns

**Focus Indicators:**
```css
:focus-visible {
  outline: 2px solid white;
  box-shadow: 0 0 0 4px #2563EB;
  outline-offset: 2px;
}
```

**Target Size:** Minimum 24×24px. Use padding to increase hit area without changing visual size.

**Dragging Alternative:** Every drag action needs a button/menu fallback.

**High Contrast Mode:**
```css
.button {
  border: 2px solid transparent; /* Preserved in forced-colors */
}
```

### Common Violations

| Issue | Fix |
|-------|-----|
| Low contrast | Darken text or lighten background |
| Missing alt | Add `alt="..."` or `alt=""` for decorative |
| Empty buttons | Add `aria-label` or visible text |
| Heading hierarchy | Don't skip levels (H2 → H4) |
| Focus traps | Implement focus loop, return focus on close |
| Placeholder as label | Always use persistent `<label>` |

### Accessibility QA Protocol

1. **Automated:** Run axe-core/Lighthouse, fix critical issues
2. **Keyboard:** Navigate entire page with Tab/Enter/Space/Arrows only
3. **Screen reader:** Test with VoiceOver/NVDA
4. **Zoom:** 200% zoom without overlap
5. **Color blindness:** Ensure color isn't only information carrier

---

## Part 8: Mobile & Touch

### Thumb Zone Ergonomics

On phones, thumbs reach different areas with different effort:

```
┌─────────────────────┐
│   HARD TO REACH     │  ← Nav, non-critical actions
├─────────────────────┤
│                     │
│   OK TO REACH       │  ← Content, secondary actions
│                     │
├─────────────────────┤
│   EASY TO REACH     │  ← Primary CTAs, bottom nav
└─────────────────────┘
```

**Rules:**
- Primary actions at bottom (FAB, bottom nav, sticky CTA)
- Destructive actions harder to reach (top, require confirmation)
- Don't put critical actions in top corners

### Touch Targets & Gestures

**Minimum Sizes:**
- Apple: 44×44pt
- Material: 48×48dp
- WCAG 2.2: 24×24px minimum

**Common Gestures:**
| Gesture | Use | Feedback |
|---------|-----|----------|
| Tap | Primary action | Visual state change |
| Long press | Secondary actions, context menu | Haptic + menu appears |
| Swipe horizontal | Navigate, delete, archive | Reveal action, snap back |
| Swipe down | Pull-to-refresh, dismiss | Loading indicator |
| Pinch | Zoom | Scale content |

**Rules:**
- Always provide visual feedback (ripple, highlight, scale)
- Swipe actions need a non-swipe alternative (accessibility)
- Long press is hidden — use sparingly, never for primary actions

### Mobile Components

**Bottom Sheet:** Modal content from bottom. Dismissible by swipe down or backdrop tap.
**Action Sheet:** List of actions from bottom. iOS pattern, use for destructive confirmations.
**Bottom Navigation:** 3-5 items max. Icons + labels. Highlight active.
**Sticky CTA:** Fixed button at bottom for primary action (checkout, submit).

### Mobile Navigation (MANDATORY)

**NEVER hide navigation on mobile.** Transform it into a mobile-appropriate pattern.

**Pattern Options:**

| Pattern | Best For | Examples |
|---------|----------|----------|
| **Hamburger → Full-screen Overlay** | Content-heavy sites, 4+ nav items | Apple, Stripe |
| **Hamburger → Slide-in Drawer** | Apps, complex navigation | Nike, Airbnb |
| **Bottom Tab Bar** | Apps, 3-5 primary destinations | iOS apps, Spotify |
| **Collapsing to Icon Row** | Simple sites, 2-3 items | Minimal blogs |

**Reference Implementations:**

**Apple.com Pattern:**
- Hamburger icon in header (right side)
- Full-screen black overlay on tap
- Large touch-friendly links
- Animated X close icon
- Search integrated

**Nike.com Pattern:**
- Hamburger opens slide-in drawer from left
- Nested accordion menus for categories
- Account/cart icons stay visible
- Swipe to close

**Stripe.com Pattern:**
- Clean hamburger → full-screen
- Links centered, large text
- Subtle fade-in animation
- Backdrop click to close

### Mobile Nav Implementation (COPY-PASTE READY)

**⚠️ USE THIS EXACT PATTERN** — It's tested and works. Don't improvise.

**HTML Structure:**
```html
<header>
  <div class="container">
    <a href="/" class="logo">Brand</a>
    <button class="nav-toggle" aria-label="Toggle menu" aria-expanded="false">
      <span></span>
      <span></span>
      <span></span>
    </button>
    <nav class="nav-links">
      <a href="#about">About</a>
      <a href="#work">Work</a>
      <a href="#contact" class="cta">Contact</a>
    </nav>
  </div>
</header>
```

**CSS (CRITICAL — class names must match exactly):**
```css
/* Desktop nav */
.nav-links {
  display: flex;
  gap: 2rem;
  align-items: center;
}

.nav-links a {
  font-size: 0.9rem;
  color: var(--text-muted);
  transition: color 0.2s;
}

.nav-links a:hover {
  color: var(--text);
}

.nav-links .cta {
  background: var(--accent);
  color: white;  /* EXPLICIT — never inherit */
  padding: 0.6rem 1.25rem;
  border-radius: 6px;
  font-weight: 500;
}

.nav-links .cta:hover {
  opacity: 0.9;
}

/* Hamburger toggle — hidden on desktop */
.nav-toggle {
  display: none;
  background: none;
  border: none;
  cursor: pointer;
  padding: 0.5rem;
  z-index: 1001;  /* Above overlay */
}

.nav-toggle span {
  display: block;
  width: 24px;
  height: 2px;
  background: var(--text);
  margin: 5px 0;
  transition: transform 0.3s, opacity 0.3s;
}

/* Hamburger → X animation */
.nav-toggle.active span:nth-child(1) {
  transform: rotate(45deg) translate(5px, 5px);
}
.nav-toggle.active span:nth-child(2) {
  opacity: 0;
}
.nav-toggle.active span:nth-child(3) {
  transform: rotate(-45deg) translate(5px, -5px);
}

/* Mobile breakpoint */
@media (max-width: 768px) {
  .nav-toggle {
    display: block;
  }
  
  .nav-links {
    display: none;  /* Hidden by default */
    position: fixed;
    inset: 0;
    background: var(--background);
    flex-direction: column;
    justify-content: center;
    align-items: center;
    gap: 2rem;
    z-index: 1000;
  }
  
  .nav-links.active {
    display: flex;  /* Shown when active */
  }
  
  .nav-links a {
    font-size: 1.5rem;
    color: var(--text);
  }
  
  .nav-links .cta {
    padding: 1rem 2rem;
    font-size: 1.25rem;
  }
}
```

**JavaScript (REQUIRED — put before closing </body>):**
```javascript
<script>
  const toggle = document.querySelector('.nav-toggle');
  const navLinks = document.querySelector('.nav-links');
  
  toggle.addEventListener('click', () => {
    const isOpen = toggle.classList.toggle('active');
    navLinks.classList.toggle('active');
    toggle.setAttribute('aria-expanded', isOpen);
    document.body.style.overflow = isOpen ? 'hidden' : '';
  });
  
  // Close menu when link clicked
  navLinks.querySelectorAll('a').forEach(link => {
    link.addEventListener('click', () => {
      toggle.classList.remove('active');
      navLinks.classList.remove('active');
      toggle.setAttribute('aria-expanded', 'false');
      document.body.style.overflow = '';
    });
  });
</script>
```

**Critical Rules:**
1. **Class names must match** — CSS uses `.nav-links`, JS queries `.nav-links`, HTML has `class="nav-links"`
2. **Z-index hierarchy** — Toggle (1001) > Nav overlay (1000) > Header (100)
3. **Explicit CTA colors** — `.nav-links .cta { color: white; }` — never rely on inheritance
4. **Body scroll lock** — Prevent background scroll when menu open
5. **Links close menu** — Every nav link tap should close the overlay

**Testing (MANDATORY before deploy):**
1. Open browser DevTools → Toggle device toolbar (mobile view)
2. Click hamburger → Menu opens full-screen
3. Click a nav link → Menu closes, navigates
4. Click hamburger again → Toggle animates to X
5. Resize to desktop → Menu reverts to horizontal row

**Implementation Checklist:**
- [ ] Menu toggle button visible on mobile (44×44px minimum)
- [ ] Toggle has aria-label and aria-expanded
- [ ] Menu overlay/drawer has proper z-index (above content)
- [ ] Body scroll locked when menu open
- [ ] Links close menu on tap
- [ ] Animated transition (150-300ms)
- [ ] X or animated hamburger-to-X for close state

**Anti-patterns:**
- ❌ Just hiding nav with `display: none` — users lose navigation entirely
- ❌ Tiny hamburger icon (<44px)
- ❌ Menu that doesn't close when link tapped
- ❌ No visual feedback on toggle
- ❌ CSS selector mismatch (using `nav` in CSS but `class="nav-links"` in HTML)
- ❌ Forgetting to add the JavaScript
- ❌ CTA buttons inheriting wrong text color

### Performance (Critical for Mobile)

50%+ of users are on mobile. Many on older devices, slow networks.

**Core Web Vitals Targets:**
| Metric | Good | What It Measures |
|--------|------|------------------|
| LCP | <2.5s | Largest content painted |
| INP | <200ms | Interaction responsiveness |
| CLS | <0.1 | Layout stability |

**Image Optimization:**
- Use WebP/AVIF (30-50% smaller than JPEG)
- Serve responsive sizes (`srcset`)
- Lazy load below-fold images
- Explicit `width`/`height` to prevent CLS

**Bundle Optimization:**
- Target <100KB JS for initial load
- Code split by route
- Tree shake unused code
- Defer non-critical scripts

**Older Device Considerations:**
- Test on 3-4 year old phones
- Reduce animation complexity (or disable with `prefers-reduced-motion`)
- Avoid heavy backdrop-filter on low-end devices
- Minimize main thread work (no heavy JS during scroll)
- Provide skeleton/placeholder states

**Network Resilience:**
- Offline states and messaging
- Retry mechanisms for failed requests
- Cache aggressively (service worker for repeat visits)
- Compress API responses (gzip/brotli)

---

## Part 9: Platform-Specific

### Apple (iOS, macOS, watchOS)

**Principles:** Clarity, Deference, Depth

**Key Patterns:**
- SF Pro / SF Compact fonts
- Dynamic Type support
- Safe areas respected
- Native components when possible
- Haptic feedback (iOS)
- 44pt minimum touch targets

### Web

**Principles:** Responsive, Performant, Progressive

**Breakpoints:**
```css
@media (min-width: 640px) { /* Tablet */ }
@media (min-width: 1024px) { /* Desktop */ }
@media (min-width: 1440px) { /* Wide */ }
```

**Mobile-first:** Design for mobile, enhance for larger screens.

---

## Part 10: Design System Governance

### Token Architecture

**Naming:** `{Category}-{Type}-{Item}-{State}`
- ✅ `color-text-primary`
- ❌ `color-blue-500`

**Tiers:**
1. **Global (Primitive):** Raw values (`blue-500: #0066CC`) — never use directly
2. **Alias (Semantic):** Context names (`color-action-primary: $blue-500`)
3. **Component:** Specific (`button-bg-primary: $color-action-primary`)

**Deprecation:** Mark deprecated → create alias → remove in next major.

### Component Lifecycle

| Stage | Requirements |
|-------|--------------|
| Proposal | Problem statement, usage examples |
| Draft (Alpha) | Basic specs, initial code. Not for production. |
| Review (Beta) | Design review, code review, basic a11y |
| Stable | 100% docs, tests, a11y audit pass |
| Deprecated | Migration guide, warnings |
| Archived | Removed |

### Change Management

- **Minor:** PR or Figma branch
- **Major:** RFC (Problem, Solution, Alternatives, Breaking?)
- **Breaking changes:** Batch into major releases, announce 1 sprint ahead, provide codemods

### Anti-Patterns

- **Token Drift:** Hardcoding hex/px instead of tokens → lint rules
- **One-off Forks:** Copy-pasting components → propose variant instead
- **Z-Index Chaos:** Arbitrary values → use tokenized z-index scale
- **Prop Explosion:** Too many props → compose or use slots
- **Unreviewed Variants:** Local components → regular harvesting sessions

---

## Part 11: Handoff & QA

### Definition of Done

- [ ] Visual parity with spec (1-2px tolerance)
- [ ] Responsive at all breakpoints + fluid between
- [ ] All states implemented (hover, focus, active, disabled, loading, error, empty)
- [ ] Content resilience (long text, missing data, RTL)
- [ ] Accessibility compliance (WCAG 2.1 AA)
- [ ] Assets optimized (SVG/WebP, lazy-loaded)
- [ ] Motion matches spec

### State Coverage Checklist

Every interactive element needs: Default, Hover, Focus, Active, Disabled, Loading, Error, Success, Empty, Partial (skeleton).

### Component QA

**Buttons:** 44px touch area, all states, icon alignment, loading doesn't resize
**Forms:** Persistent labels, focus rings, validation messages, correct mobile keyboards
**Cards:** Click area clarity, equal height rows, image fallbacks
**Modals:** Backdrop closes, scroll lock, focus trap, Escape closes

### Visual Regression

1. Snapshot baseline in Storybook/Chromatic
2. Compare on every PR
3. Approve intentional changes, reject unintentional

**Tools:** Chromatic, Percy, BackstopJS

### Cross-Browser Priority

**Tier 1:** Chrome, Safari, Firefox (latest -2)
**Tier 2:** Edge, older iOS
**Tier 3:** Samsung Internet, legacy

---

## Part 12: Anti-Patterns

### Visual
- ❌ Purple-to-blue gradients
- ❌ Glossy 3D blobs
- ❌ Generic stock illustrations
- ❌ Pure white on dark (use off-white)
- ❌ Inter/Roboto without intentional reason
- ❌ Native emoji as icons (💭🤝🌱) — always use SVG icons
- ❌ Dark text on colored button backgrounds (use white/light text)

### Structural (CRITICAL)
- ❌ All-white sections with no visual rhythm (alternate backgrounds)
- ❌ Sections breaking container bounds (maintain consistent max-width)
- ❌ Mixed alignment in centered sections (if centered, ALL elements centered)
- ❌ Header/footer indistinguishable from content sections
- ❌ Orphaned small text (helper text must match parent alignment)
- ❌ Nav buttons inheriting wrong text color (explicitly set white on colored)
- ❌ Undersized hero (hero should be outsized for impact)
- ❌ Cluttered footer with section headers (keep minimal, single row)
- ❌ Mobile nav that just disappears (must transform to hamburger/drawer)
- ❌ "Too clean" — all flat colors, no photos/textures/visual moments
- ❌ 100vh heroes (hero should show content below to invite scrolling)
- ❌ Floating labels/metadata disconnected from their content
- ❌ Grid columns that don't collapse properly on mobile
- ❌ Complex editorial layouts that break on smaller screens
- ❌ Body text below 16px (14px absolute minimum, 16px preferred)

### Section Spacing & Structure (MANDATORY)

**Minimum Section Padding:**
- Mobile: `padding: 5rem 1.5rem` minimum (80px vertical)
- Desktop: `padding: 8rem 2rem` minimum (128px vertical)
- Hero sections: `padding: 10rem+ 2rem` (160px+ vertical) — heroes need to BREATHE
- Large statement sections: `padding: 10rem 2rem` (160px vertical)

**The Stripe Standard:**
Look at Stripe.com — notice how sections have ~120-160px of vertical padding on desktop. Content floats in generous whitespace. This is the target, not cramped information density.

**Container Rules:**
```css
.container {
  max-width: 1200px;  /* Consistent across ALL sections */
  margin: 0 auto;
  padding: 0 1.5rem;  /* Mobile */
}
@media (min-width: 768px) {
  .container { padding: 0 2rem; }
}

/* Section padding - GENEROUS */
section {
  padding: 5rem 0;  /* Mobile minimum */
}
@media (min-width: 768px) {
  section { padding: 8rem 0; }  /* Desktop minimum */
}
.hero {
  padding: 10rem 0 8rem;  /* Heroes need MORE */
}
```

**Visual Hierarchy Requirements:**
1. **Clear section boundaries** — Each section should be obviously distinct
2. **Consistent container width** — Don't change max-width between sections
3. **Logical grouping** — Related content stays together, unrelated content separated
4. **Readable line lengths** — Body text max-width: 65-75ch
5. **Room to breathe** — When in doubt, add MORE whitespace, not less

**Mobile Collapse Rules:**
- Multi-column layouts MUST collapse to single column
- Grid elements stack vertically
- Floating/offset elements become inline
- Editorial "margin notes" become inline callouts
- Navigation transforms (never disappears)

**Common Mistake: Overcrowding**
Designers often try to fit too much "above the fold." This creates cramped, overwhelming layouts. Trust users to scroll — they will if the content is compelling. A bold, spacious hero converts better than a cramped one.

### Hero Height & Impact Guidelines

**Don't use `min-height: 100vh`** — it hides content and feels static.

**But heroes still need to be BOLD and IMPACTFUL:**

```css
/* Good: Generous padding, shows content below */
.hero {
  padding: 10rem 0 8rem;  /* 160px top, 128px bottom */
}

/* Good: Large but not viewport-trapping */
.hero {
  min-height: 70vh;
  max-height: 900px;
  padding: 8rem 0;
}

/* Good: Responsive hero that scales */
.hero {
  padding: clamp(6rem, 15vh, 12rem) 0;
}
```

**Hero typography should be MASSIVE:**
- Headline: `clamp(3rem, 8vw, 6rem)` or larger
- Don't be afraid of 100px+ headlines on desktop
- Let the hero breathe — generous whitespace around headline

**Hero should:**
- Make an immediate visual impact (bold type, color, imagery, or motion)
- Show a glimpse of content below (invites scrolling)
- Have generous internal spacing (not cramped)
- Feel like a statement, not a form to fill out

### Typography Minimums (MANDATORY)

| Element | Minimum Size | Preferred |
|---------|-------------|-----------|
| Body text | 16px | 16-18px |
| Secondary text | 14px | 14-16px |
| Captions/labels | 12px | 12-14px |
| Never below | 12px | — |

**Why:** Text below 16px becomes difficult to read on mobile devices. Smaller text should only be used for tertiary information (timestamps, legal text), never for body content.

### Behavioral
- ❌ Scrolljacking
- ❌ Mystery meat navigation (icons without labels)
- ❌ Layout shift (CLS)
- ❌ Slow transitions (>400ms for simple actions)
- ❌ Silent failures (no error feedback)
- ❌ No retry path for errors

### Code
- ❌ `px` for font sizes (use `rem`)
- ❌ Hardcoded colors (use tokens)
- ❌ Mixed depth strategies
- ❌ Missing hover/focus/active states
- ❌ Inconsistent icon weights
- ❌ Blocking fonts, oversized hero media

### Design System
- ❌ Token drift (hardcoded values)
- ❌ One-off component forks
- ❌ Z-index chaos
- ❌ Unreviewed variants

**The Test:** Would swapping for defaults feel different? If NO → iterate.

---

## Part 13: Quick Reference

### Pre-Flight Checklist

**Design Quality:**
- [ ] Intent statement written
- [ ] All tokens have rationale
- [ ] No anti-patterns present
- [ ] Four tests pass (Swap, Squint, Signature, Token)

**Structural Consistency:**
- [ ] All sections use same container max-width
- [ ] Sections have alternating backgrounds (visual rhythm)
- [ ] Sections have adequate padding (4rem+ vertical minimum)
- [ ] Header/footer visually distinct from content
- [ ] Centered sections have ALL elements centered
- [ ] No native emoji — SVG icons only
- [ ] Filled buttons have light text on colored backgrounds
- [ ] Mobile navigation transforms (hamburger/drawer), not disappears
- [ ] Body text is 16px minimum (14px only for tertiary info)
- [ ] Hero is NOT 100vh (shows content below to invite scrolling)
- [ ] Complex layouts collapse properly on mobile (single column)
- [ ] No floating/orphaned elements on mobile

**Visual Interest:**
- [ ] Chose ONE visual approach (A-F) that matches brand
- [ ] Applied it boldly, not timidly
- [ ] Would a non-designer notice the visual character?
- [ ] Site has a "signature moment" someone would remember

**Interactivity:**
- [ ] All interactive states defined (hover, focus, active, disabled, loading)
- [ ] Keyboard navigable
- [ ] Focus indicators visible

**Accessibility:**
- [ ] 4.5:1 contrast minimum (including button text!)
- [ ] Dark mode tested
- [ ] Reduced motion fallbacks

**Pipeline:**
- [ ] Multi-model review completed (MANDATORY)
- [ ] Review findings addressed
- [ ] Definition of Done met

### Decision Guide

| Need | Solution |
|------|----------|
| Colors | Semantic tokens with rationale |
| Forms | Labels above, inline validation |
| Navigation | Top (web), bottom tabs (mobile), sidebar (complex) |
| Data tables | Sticky headers, selection, inline edit, keyboard nav |
| iOS | SF Pro, safe areas, haptics |
| Animation | 100-200ms, ease-out |
| Loading | Skeletons for content, spinners for actions |
| Errors | Toasts recoverable, inline near problem |
| Bulk actions | Action bar + confirmation flow |
| Accessibility | Test keyboard, screen reader, zoom, color blindness |

---

*Design is decision-making. Make intentional choices, document why, validate before shipping.*
