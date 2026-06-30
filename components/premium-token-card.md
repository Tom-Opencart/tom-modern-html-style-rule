# Premium Token Card

A self-contained, visually distinctive card component for displaying tokens, codes, keys, identifiers, and other high-value short data.

Originally designed for digital activation keys, this component is generic enough for any scenario where a short alphanumeric value needs to be presented as a premium, attention-grabbing artifact.

---

## When to Use

Use this component when the content is:
- A **short alphanumeric value** (4–20 characters, optionally segmented)
- **High-value** to the user (activation key, promo code, license, access token)
- **Unique** per user/order/session (not generic placeholder text)
- Presented as a **visual artifact** (not inline text)

Typical use cases:
- Digital product activation keys
- Promo / discount codes
- License keys and serial numbers
- Order / invoice / tracking numbers
- Invite links / referral codes
- PIN codes / access tokens
- API keys in documentation
- VIP / status identifiers
- Payment card numbers (masked)
- Certificate / achievement IDs

---

## Visual Specification

### Outer Frame (`.key-card-frame`)

A white container that holds the card and optional metadata.

| Property | Value | Notes |
|---|---|---|
| `width` | `100%` | Fills parent |
| `max-width` | `390px` | Prevents overstretching |
| `padding` | `18px` | Inner breathing room |
| `border` | `2px solid` line color | Tom Modern Design line |
| `background` | `rgba(255, 255, 255, 0.93)` | Near-white, slight transparency |
| `box-shadow` | `8px 8px 0 rgba(21, 21, 21, 0.08)` | Hard offset shadow, Tom Modern style |

### Metadata Row (`.key-card-meta`)

Optional row above the card showing context labels.

| Property | Value | Notes |
|---|---|---|
| `display` | `flex` | Horizontal layout |
| `justify-content` | `space-between` | Labels at edges |
| `gap` | `12px` | Space between labels |
| `margin-bottom` | `14px` | Gap before card |
| `padding-bottom` | `10px` | Gap after border |
| `border-bottom` | `1px solid rgba(21, 21, 21, 0.14)` | Subtle separator |
| `font-family` | Mono font | IBM Plex Mono or Geist Mono |
| `font-size` | `10px` | Micro text |
| `letter-spacing` | `0.14em` | Expanded tracking |
| `text-transform` | `uppercase` | All caps |
| `color` | Muted color | `#6c675d` or equivalent |

### Card Body (`.key-card`)

The dark gradient card — the signature visual element.

| Property | Value | Notes |
|---|---|---|
| `position` | `relative` | For sheen positioning |
| `background` | `linear-gradient(155deg, #14192B 0%, #1B2A3D 55%, #11393A 100%)` | Deep navy-to-teal gradient |
| `border-radius` | `0px` | Sharp corners (Tom Modern) |
| `padding` | `24px 22px 18px` | Top/Horizontal/Bottom |
| `color` | `#EEF1F8` | Light blue-white text |
| `overflow` | `hidden` | Clips sheen |
| `isolation` | `isolate` | Stacking context |

**Gradient direction:** 155deg (top-left to bottom-right, slightly angled).

**Gradient stops:**
- `#14192B` at 0% — deep navy-black
- `#1B2A3D` at 55% — dark steel-blue
- `#11393A` at 100% — dark teal

### Holographic Sheen (`.key-card__sheen`)

A diagonal light sweep that plays once on load, creating a holographic/foil effect.

| Property | Value | Notes |
|---|---|---|
| `position` | `absolute` | Overlays card |
| `top` | `-40%` | Extends beyond card |
| `left` | `-65%` | Starts off-screen left |
| `width` | `170%` | Covers full diagonal |
| `height` | `180%` | Covers full diagonal |
| `background` | `linear-gradient(115deg, ...)` | See gradient stops below |
| `transform` | `rotate(9deg) translateX(-12%)` | Angled sweep |
| `mix-blend-mode` | `screen` | Additive blending |
| `pointer-events` | `none` | Non-interactive |
| `z-index` | `0` | Behind content |
| `animation` | `sheen-sweep 2.4s ease-out 0.2s 1` | One-time play |

**Sheen gradient stops:**
```
transparent        32%
rgba(14,124,123,0.45)  42%   — teal highlight
rgba(201,127,30,0.4)   50%   — gold highlight
rgba(255,255,255,0.3)  56%   — white peak
transparent        66%
```

**Animation keyframes:**
```css
@keyframes sheen-sweep {
    from { transform: rotate(9deg) translateX(-38%); }
    to   { transform: rotate(9deg) translateX(-12%); }
}
```

The sheen slides from left (-38%) to rest position (-12%) over 2.4 seconds with ease-out easing, starting 0.2s after load. Plays exactly once.

### Label (`.key-card__label`)

A small uppercase label above the value, typically gold/amber.

| Property | Value | Notes |
|---|---|---|
| `position` | `relative` | Above sheen |
| `z-index` | `1` | Above sheen |
| `font-family` | Mono font | IBM Plex Mono or Geist Mono |
| `font-size` | `10.5px` | Micro text |
| `letter-spacing` | `0.14em` | Expanded tracking |
| `text-transform` | `uppercase` | All caps |
| `color` | `#E8B872` | Gold/amber |
| `margin-bottom` | `12px` | Gap before value |

### Value (`.key-card__value`)

The main displayed token/key/code.

| Property | Value | Notes |
|---|---|---|
| `position` | `relative` | Above sheen |
| `z-index` | `1` | Above sheen |
| `font-family` | Mono font | IBM Plex Mono or Geist Mono |
| `font-size` | `clamp(19px, 2.1vw, 24px)` | Responsive |
| `letter-spacing` | `1px` | Slight expansion |
| `font-weight` | `500` | Medium |
| `display` | `flex` | For segmented values |
| `flex-wrap` | `wrap` | Wraps on narrow |
| `gap` | `2px` | Between segments |
| `margin-bottom` | `20px` | Gap before perforation |

**Sub-elements:**
- `.sep` — separator between segments (color: `rgba(238, 241, 248, 0.35)`, margin: `0 1px`)
- `.seg--dim` — dimmed segment for alternating emphasis (color: `rgba(238, 241, 248, 0.32)`)

### Perforation (`.key-card__perforation`)

A dashed line with circular cutouts on left and right edges, simulating a physical tear-off.

| Property | Value | Notes |
|---|---|---|
| `position` | `relative` | For pseudo-element positioning |
| `border-top` | `1px dashed rgba(238, 241, 248, 0.28)` | Dashed separator |
| `margin` | `0 -22px` | Extends to card edges |
| `padding` | `0 22px` | Content stays inset |

**Circular cutouts (pseudo-elements):**
```css
.key-card__perforation::before,
.key-card__perforation::after {
    content: "";
    position: absolute;
    top: -8px;              /* Centers on dashed line */
    width: 16px;
    height: 16px;
    border-radius: 50%;
    background: var(--surface);  /* Matches page background */
}
.key-card__perforation::before { left: -8px; }
.key-card__perforation::after  { right: -8px; }
```

The cutouts use `background: var(--surface)` to match the page background, creating the illusion of holes punched through the card.

### Footer / Chips (`.key-card__footer`)

A flex container for small metadata chips below the perforation.

| Property | Value | Notes |
|---|---|---|
| `position` | `relative` | Above sheen |
| `z-index` | `1` | Above sheen |
| `display` | `flex` | Horizontal layout |
| `gap` | `8px` | Between chips |
| `flex-wrap` | `wrap` | Wraps on narrow |
| `padding-top` | `14px` | Gap after perforation |

### Chip (`.chip`)

A small pill-shaped tag with optional icon.

| Property | Value | Notes |
|---|---|---|
| `display` | `inline-flex` | Inline with icon |
| `align-items` | `center` | Vertically centered |
| `gap` | `5px` | Icon-to-text gap |
| `font-family` | Mono font | IBM Plex Mono or Geist Mono |
| `font-size` | `10.5px` | Micro text |
| `letter-spacing` | `0.06em` | Slight expansion |
| `text-transform` | `uppercase` | All caps |
| `padding` | `5px 10px` | Inner spacing |
| `border-radius` | `999px` | Fully rounded pill |
| `border` | `1px solid rgba(238, 241, 248, 0.22)` | Subtle border |
| `color` | `#DCE2F0` | Light text |

**Icon sizing:** `width: 12px; height: 12px; flex-shrink: 0;`

---

## HTML Structure

### Minimal (value only)

```html
<div class="key-card">
    <div class="key-card__sheen"></div>
    <div class="key-card__label">Activation Key</div>
    <div class="key-card__value">
        <span>8F2C</span><span class="sep">–</span><span>ZQ91</span>
    </div>
</div>
```

### Standard (with perforation and chips)

```html
<div class="key-card">
    <div class="key-card__sheen"></div>
    <div class="key-card__label">Your License Key</div>
    <div class="key-card__value">
        <span>8F2C</span><span class="sep">–</span><span class="seg--dim">ZQ91</span>
        <span class="sep">–</span><span>K4D7</span><span class="sep">–</span><span class="seg--dim">TX5E</span>
    </div>
    <div class="key-card__perforation">
        <div class="key-card__footer">
            <span class="chip">
                <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
                    <path d="M9 12l2 2 4-4"/><circle cx="12" cy="12" r="9"/>
                </svg>
                Unique Code
            </span>
        </div>
    </div>
</div>
```

### Full (with frame and metadata)

```html
<div class="key-card-frame">
    <div class="key-card-meta">
        <span>Preview</span>
        <span>Sample</span>
    </div>
    <div class="key-card">
        <div class="key-card__sheen"></div>
        <div class="key-card__label">Activation Key</div>
        <div class="key-card__value">
            <span>8F2C</span><span class="sep">–</span><span class="seg--dim">ZQ91</span>
            <span class="sep">–</span><span>K4D7</span><span class="sep">–</span><span class="seg--dim">TX5E</span>
        </div>
        <div class="key-card__perforation">
            <div class="key-card__footer">
                <span class="chip">
                    <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
                        <path d="M9 12l2 2 4-4"/><circle cx="12" cy="12" r="9"/>
                    </svg>
                    Unique Code
                </span>
                <span class="chip">
                    <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
                        <rect x="4" y="10" width="16" height="10" rx="2"/>
                        <path d="M8 10V7a4 4 0 018 0v3"/>
                    </svg>
                    1 Code = 1 Order
                </span>
            </div>
        </div>
    </div>
</div>
```

---

## CSS Variables Used

This component references these Tom Modern Design tokens:

| Variable | Used For |
|---|---|
| `--surface` | Perforation cutout background |
| `--line` | Frame border |
| `--muted` | Meta row text |
| `--font-mono` | All monospace text |

If not using Tom Modern Design tokens, replace with literal values:
- `--surface` → `#ffffff`
- `--line` → `#1c1c1c`
- `--muted` → `#6c675d`
- `--font-mono` → `"IBM Plex Mono", "Courier New", monospace`

---

## Variations

### `.key-card--promo`

For promo codes and discount tokens. Warmer gradient, accent-colored label.

```css
.key-card--promo {
    background: linear-gradient(155deg, #2B1419 0%, #3D1B2A 55%, #3A1119 100%);
}
.key-card--promo .key-card__label {
    color: #FF6B6B;  /* Red/coral instead of gold */
}
```

### `.key-card--compact`

Narrower padding for sidebar or card-grid contexts.

```css
.key-card--compact {
    padding: 16px 14px 12px;
}
.key-card--compact .key-card__value {
    font-size: 16px;
    margin-bottom: 12px;
}
.key-card--compact .key-card__perforation {
    margin: 0 -14px;
    padding: 0 14px;
}
```

### `.key-card--inverse`

Light background for dark-mode inversion or light-context embedding.

```css
.key-card--inverse {
    background: linear-gradient(155deg, #f5f5f3 0%, #e8e8e4 55%, #eaeae6 100%);
    color: #151515;
}
.key-card--inverse .key-card__label {
    color: #B8860B;  /* Dark gold */
}
.key-card--inverse .key-card__value .sep {
    color: rgba(21, 21, 21, 0.3);
}
.key-card--inverse .key-card__value .seg--dim {
    color: rgba(21, 21, 21, 0.25);
}
.key-card--inverse .key-card__perforation {
    border-top-color: rgba(21, 21, 21, 0.2);
}
.key-card--inverse .chip {
    border-color: rgba(21, 21, 21, 0.2);
    color: #36342f;
}
```

### `.key-card--status`

For status indicators (VIP, Gold, Platinum). No perforation, icon replaces value.

```html
<div class="key-card key-card--status">
    <div class="key-card__sheen"></div>
    <div class="key-card__label">Your Status</div>
    <div class="key-card__value">
        <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" style="width:32px;height:32px;">
            <path d="M12 2l3.09 6.26L22 9.27l-5 4.87 1.18 6.88L12 17.77l-6.18 3.25L7 14.14 2 9.27l6.91-1.01L12 2z"/>
        </svg>
        Gold
    </div>
</div>
```

### `.key-card--payment`

For masked payment card display.

```html
<div class="key-card">
    <div class="key-card__sheen"></div>
    <div class="key-card__label">Payment Method</div>
    <div class="key-card__value">
        <span class="seg--dim">••••</span><span class="sep"> </span>
        <span class="seg--dim">••••</span><span class="sep"> </span>
        <span class="seg--dim">••••</span><span class="sep"> </span>
        <span>4829</span>
    </div>
    <div class="key-card__perforation">
        <div class="key-card__footer">
            <span class="chip">Visa</span>
            <span class="chip">Exp 12/28</span>
        </div>
    </div>
</div>
```

---

## Responsive Behavior

| Breakpoint | Changes |
|---|---|
| `< 860px` | `.key-card-frame` padding → `14px`; `.key-card-meta` → column layout |
| `< 480px` | `.key-card__value` font-size clamps to `19px`; chips stack vertically |

---

## Accessibility

- The sheen animation respects `prefers-reduced-motion: reduce` — it stops at rest position.
- The card has no interactive elements by default. If wrapping in a link, add `role="link"` and appropriate `aria-label`.
- The perforation cutouts are purely decorative — no ARIA needed.

---

## Agent Instructions

When an AI agent needs to render this component:

1. **Always include `.key-card__sheen`** — even if animation is disabled, the rest position provides subtle highlight.
2. **Use mono font for all text** — label, value, chips. Never use sans-serif inside the card.
3. **Segment long values** — split into 4-character groups with `.sep` dashes and alternating `.seg--dim` for visual rhythm.
4. **Match perforation background to page** — `background: var(--surface)` must match the actual page background color.
5. **Keep max-width ≤ 390px** — the card is designed for compact display, not full-width.
6. **One card per section** — do not place multiple premium token cards side by side. Use a single card as a focal point.
7. **Preserve the gradient** — do not replace with solid colors. The navy-to-teal gradient is the signature.
8. **Sheen plays once** — do not loop the animation. `animation-iteration-count: 1`.
