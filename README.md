# Tom Modern HTML Style Rule

Public rule set, design system, and ready-to-use templates for LLMs and coding agents that need to create HTML in Tom's accepted modern design style.

Current trigger word:
- `современный дизайн`

---

## Quick Start for AI Agents

**To reproduce Tom Modern Design exactly:**

1. Load `tom-modern.css` — the complete design system with all tokens and components
2. Copy blocks from `templates/` — ready-to-use HTML for each component
3. Reference `tom-modern-html-style-rule.md` — principles and guidelines

```html
<!-- Step 1: Load fonts -->
<link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/geist@1.3.1/dist/fonts/geist-sans/style.css">
<link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/geist@1.3.1/dist/fonts/geist-mono/style.css">

<!-- Step 2: Load design system -->
<link rel="stylesheet" href="tom-modern.css">

<!-- Step 3: Copy a template -->
<!-- See templates/ folder -->
```

---

## Files

| File | Purpose |
|---|---|
| `tom-modern.css` | Complete CSS design system (tokens + all components) |
| `tom-modern-html-style-rule.md` | Design principles and guidelines |
| `quick-start.html` | Example page using the design system |
| `index.html` | Live component preview |
| `components/premium-token-card.md` | Token card specification |
| `components/premium-code-window.md` | Code window specification |
| `templates/` | Ready-to-use HTML blocks |

---

## Templates

| Template | Description |
|---|---|
| `hero.html` | Hero section with dashboard visual |
| `trust-band.html` | Metrics strip with integrations |
| `feature-grid.html` | 2-column feature grid with wide cards |
| `feature-3col.html` | 3-column feature grid with icons |
| `definition-grid.html` | Definition list + aside panel |
| `workflow.html` | Timeline steps + diagram |
| `updates.html` | 6-card updates grid |
| `pain-points.html` | 3-card pain points grid |
| `tabs.html` | Tabbed content panels |
| `pricing.html` | Pricing card |
| `faq.html` | FAQ accordion (requires JS) |
| `proof.html` | Quotes + comparison table |
| `contact.html` | Contact form |
| `footer.html` | Site footer |
| `readout-strip.html` | 3-column metric tiles |
| `panel.html` | Content panel with list |
| `spec-list.html` | Specification rows |
| `token-card.html` | Premium token card |
| `code-window.html` | Premium code window |

---

## Design Tokens

```css
:root {
    --tm-bg: #fafafa;           /* Page background */
    --tm-surface: #ffffff;       /* Card/panel surface */
    --tm-surface-alt: #f4f4f5;   /* Alternate surface */
    --tm-text: #27272a;          /* Primary text */
    --tm-text-secondary: #52525b; /* Secondary text */
    --tm-muted: #71717a;         /* Muted text */
    --tm-line: #969696;          /* Border color */
    --tm-line-muted: #d4d4d8;    /* Muted border */
    --tm-accent: #ff5a00;        /* Accent (vermillion) */
    --tm-shadow-hard: 8px 8px 0 rgba(150, 150, 150, 0.12);
    --tm-shadow-soft: 4px 4px 0 rgba(150, 150, 150, 0.1);
    --tm-font-sans: 'Geist Sans', system-ui, sans-serif;
    --tm-font-mono: 'Geist Mono', ui-monospace, monospace;
}
```

---

## Component CSS Classes

### Layout
- `.container` — centered max-width container
- `.section` — vertical padding section
- `.section-alt` — alternate background section
- `.frame` — card with border and shadow

### Typography
- `.eyebrow` — uppercase mono label
- `.title-highlight` — accent-colored text span
- `.section-head` — section header with title and description

### Buttons
- `.button` — base button
- `.button-primary` — dark filled button
- `.button-secondary` — transparent outlined button
- `.button-block` — full-width button

### Hero
- `.hero-grid` — 2-column hero layout
- `.hero-lead` — lead paragraph
- `.hero-actions` — button group
- `.hero-notes` — bullet list of key points

### Trust
- `.trust-band` — metrics strip
- `.trust-metrics` — metric items
- `.trust-platforms` — integration logos

### Features
- `.feature-grid` — 2-column grid (with `.feature-card-wide` for full-width)
- `.feature-3col` — 3-column grid with icons
- `.feature-meta` — category label

### Workflow
- `.timeline` — numbered steps
- `.diagram` — input → process → output diagram

### Tabs
- `.tab-shell` — tab container
- `.tab-nav` — tab buttons
- `.tab-button` — individual tab (add `.is-active`)
- `.tab-panel` — tab content (add `.is-active`)

### FAQ
- `.faq-list` — accordion container
- `.faq-item` — individual item (add `.is-open`)
- `.faq-question` — clickable question
- `.faq-answer` — hidden answer

### Forms
- `.contact-grid` — 2-column form layout
- `.field-group` — label + input group
- `.form-control` — input/textarea

### Pricing
- `.pricing-grid` — 2-column pricing layout
- `.pricing-card` — pricing card
- `.pricing-head` — price display

### Proof
- `.proof-grid` — 2-column proof layout
- `.quote-stack` — testimonial cards
- `.comparison` — comparison table

### Premium Components
- `.key-card-frame` → `.key-card` → `.key-card__sheen` + `.key-card__label` + `.key-card__value`
- `.tm-code-window` → `.tm-code-header` + `.tm-code-body`

---

## Live Preview

**[View Component Preview →](https://tom-opencart.github.io/tom-modern-html-style-rule/)**

---

## Agent Instructions

When an AI agent needs to create a page in Tom Modern Design:

1. **Load the CSS**: `<link rel="stylesheet" href="tom-modern.css">`
2. **Use templates**: Copy from `templates/` and replace content
3. **Use accent word**: One `<span class="title-highlight">word</span>` per headline
4. **Use `.frame` class**: For all cards and panels
5. **Use `.eyebrow` class**: For section labels
6. **Use CSS variables**: Never hardcode colors — use `var(--tm-accent)` etc.
7. **Sharp corners**: Never add border-radius — the design is 0px corners
8. **Neutral background**: Use `#fafafa` — never beige/cream
9. **Geist font**: Use `'Geist Sans'` for body, `'Geist Mono'` for labels/code
10. **Hard shadows**: Use `var(--tm-shadow-hard)` for hover effects
