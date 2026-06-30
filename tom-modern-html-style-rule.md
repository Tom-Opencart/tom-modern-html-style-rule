# Tom Modern Design Rule v2

Use this file as the authoritative instruction set for LLMs and coding agents when the task is to create HTML in the **same design class as Tom's `современный дизайн` rule**.

This file is not a loose moodboard.
It is an execution rule.

It can also be used as the source text for a reusable skill or system instruction.

It is intended to reproduce the same working direction used in Tom's global rules for:
- `современный дизайн`
- HTML-first visual work
- anti-slop layout quality
- OpenCart-aware adaptation workflow

Current trigger phrase:
- `современный дизайн`

This trigger phrase is configurable and may be changed later.

---

## 1. What This Rule Means

This file may be used in two ways:
- as a direct system instruction for another LLM or agent
- as the body/reference for a reusable skill such as `tom-modern-design`

When the user asks for `современный дизайн`, the agent must not interpret that as:
- “make it prettier”
- “make it more modern in any way you like”
- “invent a trendy design”

The correct meaning is:

Create a result in Tom's accepted **modern editorial-technical design family**:
- structured
- sharp
- restrained
- premium
- modern
- intentional
- anti-generic

The result must look like a page that was designed deliberately, not mass-generated.

---

## 2. Primary Output Types

This rule applies to:
- landing pages
- promo pages
- HTML descriptions
- module presentation pages
- standalone HTML references
- layout-first mockups that will later be adapted into OpenCart

If the task is visual and HTML-based, this rule is applicable by default.

---

## 3. Core Style Identity

The canonical design family is:
- editorial + technical
- modern but restrained
- light or near-light by default
- high-contrast typography
- structured composition
- clean rhythm
- deliberate geometry

Typical signals:
- Geist / Geist Mono style typography
- compact uppercase labels
- strong hierarchy
- technical grid or subtle structural background
- sharp sections
- split-layout composition
- demo-style blocks instead of fake screenshots when possible
- premium minimalism without startup-template cliches

This is **not** equivalent to a pure `Swiss Kinetic` label.

It overlaps with:
- Swiss discipline
- editorial structure
- technical minimalism
- OpenCart-native practical UX

But the actual target is broader and more specific than “Swiss Kinetic”.

---

## 4. Hard Visual Rules

### 4.1 No AI Slop

Do not generate pages that look like generic AI landing pages.

Default failure patterns:
- centered badge + huge headline + subtext + 2 buttons hero
- purple gradients by default
- random blurred blobs
- identical feature-card grids
- fake SaaS startup page with no structure
- “modern” only because it has rounded cards and glow

If the page looks interchangeable with mass AI-generated startup pages, it fails.

### 4.2 Typography Must Do Real Work

Typography is a primary design system layer.

Required:
- clear display/body/label contrast
- meaningful section labels
- compact uppercase micro-headings where useful
- controlled line length
- strong hierarchy without oversized chaos

Preferred:
- `Geist` for main typography
- `Geist Mono` for labels, technical notes, metadata, UI microcopy

Avoid:
- weak heading hierarchy
- default browser-looking type systems
- decorative fonts unless explicitly requested

### 4.3 Layout Must Be Structured

Prefer:
- split hero layouts
- framed sections
- asymmetry where justified
- alternating section densities
- rhythm between large quiet zones and dense information zones
- strong grouping and composition

Avoid:
- one repetitive vertical stack
- same card pattern in every section
- equal-width everything
- flat generic section flow

### 4.4 Color Must Be Restrained

Use:
- one primary accent
- mostly neutral supporting palette
- strong text contrast
- subtle separators and structure

Avoid:
- many accent colors
- uncontrolled neon
- loud visual noise
- dark mode by default unless task or donor requires it

**Background colors must be neutral, not warm.**

Use neutral grays and whites for page backgrounds and surfaces. Do not use beige, cream, ivory, or other warm tones.

| Token | Correct | Wrong |
|---|---|---|
| Page background | `#fafafa`, `#f5f5f5`, `#f7f7f7` | `#f4f1ea`, `#f5f0e8`, `#faf5ed` |
| Surface | `#ffffff`, `#fcfcfc` | `#fffaf1`, `#fff8f0`, `#fdf6ee` |
| Surface alt | `#f4f4f5`, `#f5f5f5` | `#f5f0e8`, `#eee8da` |
| Muted text | `#71717a`, `#717171`, `#6b6b6b` | `#69645b`, `#8a7e6b` |

This rule exists because warm beige tones make the design feel dated and "soft" — the Tom Modern aesthetic is clean, neutral, and precise.

**Canonical color palette** (from production reference):

```css
:root {
    --bg-color: #fafafa;
    --bg-grid: rgba(150, 150, 150, 0.04);
    --surface-color: #ffffff;
    --surface-alt: #f4f4f5;
    --border-color: #969696;
    --border-muted: #d4d4d8;
    --text-primary: #27272a;
    --text-secondary: #52525b;
    --text-muted: #71717a;
    --accent-color: #ff5a00;
    --accent-soft: rgba(255, 90, 0, 0.08);
    --shadow-hard: 8px 8px 0 rgba(150, 150, 150, 0.12);
    --shadow-soft: 4px 4px 0 rgba(150, 150, 150, 0.1);
}
```

### 4.5 Background Must Build Atmosphere

Prefer:
- subtle grids
- structural lines
- mild texture
- quiet gradient depth
- architectural framing

Avoid:
- empty flat background with no atmosphere
- background effects as the only design idea
- loud blob compositions
- warm beige/cream background colors

### 4.6 Components Must Feel Designed

Buttons, cards, metrics, callouts, feature blocks, previews, demos, and content panels must have clear hierarchy and visual purpose.

Avoid:
- default Bootstrap look
- default Tailwind look
- "rounded everything"
- no distinction between primary and secondary actions

### 4.7 Accent Word Pattern

Highlight one keyword in a headline with the primary accent color.

Use sparingly — one accent word per section maximum.

```html
<h1>Token Extraction <span style="color: var(--accent-color)">Engine</span></h1>
```

Prefer:
- Single word, not phrases
- The most important/brand-defining word
- Only in hero or section headlines

Avoid:
- Multiple accent words in one heading
- Accent words in body text
- Accent words that break reading flow

### 4.8 Premium Token Card

A signature dark-gradient card for displaying tokens, codes, keys, and identifiers.

This component uses a navy-to-teal gradient, holographic sheen animation, mono typography, perforation line with circular cutouts, and pill-shaped chips. It is designed for any scenario where a short alphanumeric value needs to be presented as a premium visual artifact.

**Full specification:** [`components/premium-token-card.md`](components/premium-token-card.md)

**When to use:** activation keys, promo codes, license keys, order/tracking numbers, invite links, PIN codes, API keys, payment card numbers, status identifiers.

**Quick HTML:**
```html
<div class="key-card">
    <div class="key-card__sheen"></div>
    <div class="key-card__label">Label</div>
    <div class="key-card__value">
        <span>8F2C</span><span class="sep">–</span><span class="seg--dim">ZQ91</span>
    </div>
    <div class="key-card__perforation">
        <div class="key-card__footer">
            <span class="chip">Metadata</span>
        </div>
    </div>
</div>
```

### 4.9 Premium Code Window

A dark-themed code display component that mimics a native editor window.

This component uses a deep blue-black background, macOS-style traffic light dots, atmospheric gradient overlay, and seven syntax highlighting tokens. It is designed for any scenario where code needs to be presented as a premium visual artifact.

**Full specification:** [`components/premium-code-window.md`](components/premium-code-window.md)

**When to use:** API documentation, configuration snippets, CSS/HTML examples, SQL schemas, JSON/YAML blocks, shell commands, plugin code samples, tutorial steps.

**Quick HTML:**
```html
<div class="tm-code-window">
    <div class="tm-code-header">
        <span class="tm-code-dots" aria-hidden="true">
            <span></span><span></span><span></span>
        </span>
        <span class="tm-code-title">example.js</span>
    </div>
    <div class="tm-code-body">
<pre><code><span class="token-keyword">const</span> x = <span class="token-number">42</span>;</code></pre>
    </div>
</div>
```

---

## 5. HTML-First Workflow

For visual work, prefer HTML-first execution.

That means:
1. build or refine the layout in standalone HTML first
2. get the visual direction right there
3. only then adapt into OpenCart if needed

Do not jump straight into Twig unless the task explicitly requires skipping the HTML stage.

Default scaffold:
- `index.html`
- `style.css`

Rules:
- semantic HTML
- real copy, not lorem ipsum
- no inline styling unless there is a strong reason
- meaningful `id` values for important sections
- CSS should be organized for later adaptation

---

## 6. OpenCart Branching Rule

This rule has two branches.

### 6.1 Standalone HTML / Landing / Description Branch

This branch may fully use the stronger visual identity:
- technical backgrounds
- strong hero composition
- split layouts
- animated or demo-style sections
- editorial rhythm

### 6.2 OpenCart Admin / Native Module Branch

If the output is an OpenCart admin page or module control panel:
- preserve OpenCart admin shell
- preserve settings-page ergonomics
- do not turn it into a foreign dashboard
- keep Bootstrap 3 compatibility in structure
- apply modern design as an internal refinement layer

In this branch:
- OpenCart usability is a hard constraint
- modern styling improves the module interior
- do not force landing-page composition patterns onto admin settings UI

---

## 7. Responsive Requirement

Responsive quality is mandatory.

The mobile version must be intentionally designed, not merely tolerated.

Required:
- no cramped CTA groups
- no overlapping decorative labels
- no unreadable body text
- no broken hero composition
- no horizontal overflow
- no collapsed spacing rhythm

If desktop is good but mobile is weak, the task is incomplete.

---

## 8. Motion Rule

Animation is optional and must be meaningful.

Use motion only when it improves:
- structure
- clarity
- emphasis
- perceived polish

Prefer:
- restrained reveal motion
- controlled easing
- small hover transitions
- lightweight structural animation

Avoid:
- decorative motion everywhere
- distracting movement
- sluggish or overlong transitions
- motion used as a substitute for good layout

If motion harms clarity, reduce it or remove it.

---

## 9. Preferred Visual Signals

Good signals:
- editorial-meets-technical composition
- strong type rhythm
- subtle grid structure
- deliberate section framing
- compact labels
- serious spacing discipline
- clear information hierarchy
- premium restraint

Bad signals:
- startup template hero
- too many pills
- too many same-size cards
- soft pastel SaaS cliches
- random illustrations with no structural role
- “modern” only because of glow and gradients

---

## 10. Implementation Expectations

The result should be:
- clean enough to keep as a visual reference
- structured enough to adapt into production later
- distinctive enough not to look generic
- practical enough to survive real usage

If the page includes screenshots or previews:
- prefer building convincing native demo blocks
- do not rely on fake browser screenshots as a crutch unless the task specifically wants them

---

## 11. OpenCart Adaptation Rule

If this HTML is later adapted into OpenCart:
- treat the approved HTML as the visual source of truth
- do not re-invent the style during adaptation
- preserve hierarchy, spacing logic, and visual family
- adapt technically into Twig/PHP/language files later as a separate stage

Do not assume standalone HTML can be pasted into OpenCart unchanged.

---

## 12. Decision Rule For Agents

When asked for `современный дизайн`, the agent must:

1. choose a deliberate, structured composition
2. let typography and layout carry the design
3. use accent color sparingly
4. avoid generic AI landing-page patterns
5. preserve the correct branch:
   - stronger visual branch for standalone HTML
   - OpenCart-native branch for admin/module UIs
6. verify desktop and mobile before claiming completion

If forced to choose between:
- flashy but generic
- restrained but intentional

choose:
- restrained but intentional

---

## 13. Acceptance Test

The result passes only if all of these are true:

- it does not look like generic AI-generated HTML
- it has clear hierarchy and structural rhythm
- typography feels intentional
- layout has composition, not just stacked blocks
- accent use is restrained
- desktop and mobile both work
- the page belongs to Tom's accepted `современный дизайн` family

If any of those fail, revise before approval.

---

## 14. Short Identity Label

If a short style label is needed, use one of these:
- `Tom Modern Design`
- `Tom Modern HTML`
- `OpenCart Modern Editorial-Technical`

Do **not** reduce this rule to just:
- `Swiss Kinetic`

because that label is too narrow and does not fully describe the actual accepted style.
