# Premium Code Window

A self-contained, visually distinctive code display component for documentation, landing pages, technical examples, and developer-facing content.

Originally designed for code snippets in product descriptions, this component mimics a native code editor window with macOS-style chrome, syntax highlighting tokens, and atmospheric depth effects.

---

## When to Use

Use this component when the content is:
- A **code snippet** (HTML, CSS, JS, PHP, SQL, JSON, or any language)
- **Technical** in nature (API examples, configuration, documentation)
- Presented as a **visual artifact** (not inline `<code>` text)
- Part of a **premium layout** (landing pages, module descriptions, documentation)

Typical use cases:
- API documentation with request/response examples
- Configuration file snippets (`.env`, `config.php`, `webpack.config.js`)
- CSS/HTML code examples in design system docs
- SQL schema definitions
- JSON/YAML configuration blocks
- Shell commands and CLI examples
- Plugin/module code samples
- Tutorial step-by-step code blocks

---

## Visual Specification

### Outer Container (`.tm-code-window`)

The main dark container that holds the entire code window.

| Property | Value | Notes |
|---|---|---|
| `position` | `relative` | For gradient overlay |
| `margin` | `0` | No external spacing |
| `overflow` | `hidden` | Clips gradient overlay |
| `border` | `1px solid rgba(17, 21, 23, 0.12)` | Subtle outer border |
| `background` | `var(--tm-code-bg)` → `#111517` | Deep dark blue-black |
| `box-shadow` | `var(--tm-shadow)` → `0 28px 90px rgba(22, 22, 22, 0.14)` | Heavy atmospheric shadow |

**No border-radius** — sharp corners (Tom Modern Design rule).

### Atmospheric Overlay (`.tm-code-window::before`)

A pseudo-element that adds subtle light effects for depth and atmosphere.

```css
.tm-code-window::before {
    content: "";
    position: absolute;
    inset: 0;
    pointer-events: none;
    background:
        linear-gradient(120deg, rgba(255, 255, 255, 0.08), transparent 34%),
        radial-gradient(circle at 80% 0%, rgba(92, 207, 230, 0.12), transparent 30%);
}
```

**Two layers:**
1. **Linear gradient** — subtle white highlight from top-left, fading at 34%
2. **Radial gradient** — soft cyan glow at top-right corner

This creates the illusion of light falling on a physical surface.

### Header Bar (`.tm-code-header`)

The title bar with window dots and filename.

| Property | Value | Notes |
|---|---|---|
| `position` | `relative` | Above overlay |
| `z-index` | `1` | Above overlay |
| `display` | `flex` | Horizontal layout |
| `align-items` | `center` | Vertically centered |
| `gap` | `14px` | Dots-to-title gap |
| `min-height` | `44px` | Fixed header height |
| `padding` | `0 18px` | Horizontal padding |
| `border-bottom` | `1px solid rgba(255, 255, 255, 0.08)` | Subtle separator |
| `background` | `var(--tm-code-panel)` → `#151a1d` | Slightly lighter than body |

### Window Dots (`.tm-code-dots`)

macOS-style traffic light buttons.

| Property | Value | Notes |
|---|---|---|
| `display` | `inline-flex` | Horizontal layout |
| `gap` | `8px` | Between dots |
| `flex` | `0 0 auto` | No grow/shrink |

**Dot sizing:** `width: 11px; height: 11px; border-radius: 50%;`

**Dot colors:**
- 1st dot: `#ff5f57` (red — close)
- 2nd dot: `#ffbd2e` (yellow — minimize)
- 3rd dot: `#28c840` (green — maximize)

### Title Text (`.tm-code-title`)

The filename or label in the header bar.

| Property | Value | Notes |
|---|---|---|
| `overflow` | `hidden` | Clips long names |
| `color` | `rgba(238, 242, 245, 0.58)` | Semi-transparent light |
| `font-family` | Mono font | Geist Mono, IBM Plex Mono |
| `font-size` | `12px` | Small text |
| `font-weight` | `800` | Extra bold |
| `letter-spacing` | `0.08em` | Slight expansion |
| `text-overflow` | `ellipsis` | Truncates with `...` |
| `text-transform` | `uppercase` | All caps |
| `white-space` | `nowrap` | Single line |

### Code Body (`.tm-code-body`)

The scrollable code content area.

| Property | Value | Notes |
|---|---|---|
| `position` | `relative` | Above overlay |
| `z-index` | `1` | Above overlay |
| `overflow-x` | `auto` | Horizontal scroll for long lines |
| `padding` | `24px` | Inner spacing |

### Code Block (`.tm-code-body pre`, `.tm-code-body code`)

The actual code content.

**pre:**
| Property | Value | Notes |
|---|---|---|
| `margin` | `0` | No default margin |

**code:**
| Property | Value | Notes |
|---|---|---|
| `display` | `block` | Full-width block |
| `min-width` | `max-content` | Prevents wrapping |
| `color` | `var(--tm-code-text)` → `#d8dee9` | Light gray text |
| `font-family` | Mono font | Geist Mono, IBM Plex Mono |
| `font-size` | `14px` | Readable size |
| `line-height` | `1.72` | Comfortable spacing |
| `tab-size` | `2` | 2-space indentation |

---

## Syntax Highlighting Tokens

Seven token classes for code syntax coloring. Inspired by One Dark / Nord color schemes.

| Token | Color | Hex | Use |
|---|---|---|---|
| `.token-keyword` | Yellow | `#ffd866` | `const`, `let`, `function`, `return`, `if`, `async`, `await` |
| `.token-function` | Cyan | `#5ccfe6` | Function names, method calls |
| `.token-string` | Green | `#a6e3a1` | String literals, template strings |
| `.token-number` | Purple | `#c792ea` | Numeric literals, booleans |
| `.token-property` | Blue | `#82aaff` | Object properties, variable names |
| `.token-comment` | Gray | `#6f7b86` | Comments (`//`, `/* */`, `#`) |
| `.token-punctuation` | Light gray | `#aab2bf` | Brackets, semicolons, operators |

**Base text color** (unstyled): `#d8dee9` (Nord-like light gray)

---

## HTML Structure

### Minimal (code only)

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

### Standard (with syntax highlighting)

```html
<div class="tm-code-window">
    <div class="tm-code-header">
        <span class="tm-code-dots" aria-hidden="true">
            <span></span><span></span><span></span>
        </span>
        <span class="tm-code-title">config.php</span>
    </div>
    <div class="tm-code-body">
<pre><code><span class="token-comment">// Database configuration</span>
<span class="token-keyword">return</span> [
    <span class="token-property">'host'</span>     =&gt; <span class="token-string">'localhost'</span>,
    <span class="token-property">'database'</span>  =&gt; <span class="token-string">'opencart'</span>,
    <span class="token-property">'username'</span>  =&gt; <span class="token-string">'root'</span>,
    <span class="token-property">'password'</span>  =&gt; <span class="token-string">''</span>,
];</code></pre>
    </div>
</div>
```

### With Figure Caption

```html
<figure class="tm-code-window" aria-labelledby="code-title">
    <figcaption class="tm-code-header">
        <span class="tm-code-dots" aria-hidden="true">
            <span></span><span></span><span></span>
        </span>
        <span class="tm-code-title" id="code-title">schema.sql</span>
    </figcaption>
    <div class="tm-code-body">
<pre><code><span class="token-keyword">CREATE TABLE</span> <span class="token-function">oc_dc_code</span> (
    <span class="token-property">id</span>         <span class="token-keyword">INT</span> <span class="token-keyword">AUTO_INCREMENT</span>,
    <span class="token-property">product_id</span> <span class="token-keyword">INT</span> <span class="token-keyword">NOT NULL</span>,
    <span class="token-property">code</span>       <span class="token-keyword">VARCHAR</span>(<span class="token-number">64</span>) <span class="token-keyword">NOT NULL</span>,
    <span class="token-keyword">PRIMARY KEY</span> (<span class="token-property">id</span>)
);</code></pre>
    </div>
</div>
```

---

## CSS Variables Used

This component references these Tom Modern Design tokens:

| Variable | Used For | Fallback |
|---|---|---|
| `--tm-code-bg` | Window background | `#111517` |
| `--tm-code-panel` | Header background | `#151a1d` |
| `--tm-code-text` | Code text color | `#d8dee9` |
| `--tm-shadow` | Window shadow | `0 28px 90px rgba(22, 22, 22, 0.14)` |
| `--tm-font-mono` | Monospace font | `"Geist Mono", "IBM Plex Mono", ui-monospace, monospace` |

---

## Variations

### `.tm-code-window--light`

Light theme for contexts where dark windows clash.

```css
.tm-code-window--light {
    --tm-code-bg: #fafaf8;
    --tm-code-panel: #f0f0ec;
    --tm-code-text: #2e3440;
    box-shadow: 0 28px 90px rgba(22, 22, 22, 0.08);
}
.tm-code-window--light::before {
    background:
        linear-gradient(120deg, rgba(255, 255, 255, 0.4), transparent 34%);
}
.tm-code-window--light .tm-code-header {
    border-bottom-color: rgba(22, 22, 22, 0.1);
}
.tm-code-window--light .tm-code-title {
    color: rgba(22, 22, 22, 0.5);
}
.tm-code-window--light .token-keyword { color: #b58900; }
.tm-code-window--light .token-function { color: #268bd2; }
.tm-code-window--light .token-string { color: #2aa198; }
.tm-code-window--light .token-number { color: #6c71c4; }
.tm-code-window--light .token-property { color: #268bd2; }
.tm-code-window--light .token-comment { color: #93a1a1; }
.tm-code-window--light .token-punctuation { color: #586e75; }
```

### `.tm-code-window--compact`

Smaller padding for tight layouts.

```css
.tm-code-window--compact .tm-code-header {
    min-height: 36px;
    padding: 0 14px;
    gap: 10px;
}
.tm-code-window--compact .tm-code-dots span {
    width: 9px;
    height: 9px;
}
.tm-code-window--compact .tm-code-body {
    padding: 16px;
}
.tm-code-window--compact .tm-code-body code {
    font-size: 13px;
    line-height: 1.6;
}
```

### `.tm-code-window--no-dots`

Header without traffic light dots (for non-macOS contexts).

```css
.tm-code-window--no-dots .tm-code-dots {
    display: none;
}
```

### `.tm-code-window--terminal`

Terminal style — no dots, green-on-black text.

```css
.tm-code-window--terminal {
    --tm-code-bg: #0a0e0f;
    --tm-code-panel: #0a0e0f;
    --tm-code-text: #00ff41;
}
.tm-code-window--terminal .tm-code-dots {
    display: none;
}
.tm-code-window--terminal .tm-code-title {
    color: rgba(0, 255, 65, 0.5);
}
.tm-code-window--terminal .tm-code-header {
    border-bottom-color: rgba(0, 255, 65, 0.15);
}
```

---

## Responsive Behavior

| Breakpoint | Changes |
|---|---|
| `< 560px` | Header `min-height` → `40px`, padding → `0 14px`; Body padding → `18px 14px`; Code `font-size` → `13px` |

---

## Accessibility

- Use `<figure>` + `<figcaption>` with `aria-labelledby` for semantic structure.
- Window dots are decorative — use `aria-hidden="true"`.
- Code content is plain text — screen readers read it naturally.
- The atmospheric overlay is decorative — `pointer-events: none`.

---

## Agent Instructions

When an AI agent needs to render this component:

1. **Always include the three dots** — they are the visual signature of the component.
2. **Use mono font for everything** — header title, code content. Never use sans-serif inside the window.
3. **Include the atmospheric overlay** — the `::before` pseudo-element with gradient. It provides depth.
4. **Use real code** — never placeholder text like `// your code here`. Use actual relevant snippets.
5. **Apply syntax tokens** — at minimum highlight keywords and strings. Full tokenization is preferred.
6. **Keep `min-width: max-content` on code** — this enables horizontal scroll instead of wrapping.
7. **Title should be a real filename** — `config.php`, `schema.sql`, `index.js` — not "Code" or "Example".
8. **One window per section** — do not place multiple code windows side by side. Use a single window as a focal point.
9. **Preserve the dark background** — do not replace with solid black. The `#111517` blue-black is the signature.
10. **Shadow is atmospheric** — the heavy `0 28px 90px` shadow creates depth. Do not lighten it.
