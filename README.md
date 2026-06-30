# Tom Modern HTML Style Rule

Public rule set and skill template for LLMs and coding agents that need to create HTML in Tom's accepted modern design style.

Current trigger word:
- `современный дизайн`

This trigger is configurable.
If you want another trigger phrase, change it in `SKILL.md` and in the rule text.

---

## What This Skill Produces

When activated, this skill generates HTML in **Tom Modern Design** — an editorial-technical design family that is structured, sharp, restrained, premium, and intentional.

### Design Characteristics

- **Typography:** Geist / Geist Mono or IBM Plex Sans / IBM Plex Mono
- **Colors:** One primary accent, neutral supporting palette, strong contrast
- **Layout:** Structured composition, split heroes, framed sections, asymmetry where justified
- **Corners:** Sharp 0px (no rounded Bootstrap/Tailwind look)
- **Backgrounds:** Subtle grids, structural lines, quiet gradient depth
- **Shadows:** Hard offset shadows (not soft Material elevation)

---

## Live Preview

**[View Component Preview →](https://tom-opencart.github.io/tom-modern-html-style-rule/)**

Interactive demo of all components: Accent Word, Premium Token Card, Premium Code Window, Readout Strip, Panels, Feature Grid, Spec List, and Buttons.

---

## Component Library

The skill includes two reusable signature components:

### Premium Token Card (`components/premium-token-card.md`)

For displaying tokens, codes, keys, and identifiers.

**Use cases:**
- Digital product activation keys
- Promo / discount codes
- License keys and serial numbers
- Order / invoice / tracking numbers
- Invite links / referral codes
- PIN codes / access tokens
- API keys in documentation
- Payment card numbers (masked)
- VIP / status identifiers

**Variations:** default, promo, compact, inverse, status, payment

### Premium Code Window (`components/premium-code-window.md`)

For displaying code snippets with syntax highlighting.

**Use cases:**
- API documentation examples
- Configuration file snippets
- CSS/HTML code examples
- SQL schema definitions
- JSON/YAML configuration blocks
- Shell commands and CLI examples
- Plugin/module code samples

**Variations:** default, light, compact, no-dots, terminal

---

## Sections Covered

| # | Section | What It Captures |
|---|---|---|
| 1 | What This Rule Means | Scope and intent |
| 2 | Primary Output Types | Landing pages, descriptions, modules |
| 3 | Core Style Identity | Editorial-technical design family |
| 4 | Hard Visual Rules | No AI slop, typography, layout, color, background, components |
| 4.7 | Accent Word Pattern | Single keyword highlight in headlines |
| 4.8 | Premium Token Card | Dark-gradient card for codes/keys |
| 4.9 | Premium Code Window | Dark code editor display |
| 5 | HTML-First Workflow | Build in HTML first, then adapt |
| 6 | OpenCart Branching | Standalone vs admin/module branches |
| 7 | Responsive Requirement | Mobile-first mandatory |
| 8 | Motion Rule | Meaningful animation only |
| 9 | Preferred Visual Signals | Good vs bad patterns |
| 10 | Implementation Expectations | Quality bar |
| 11 | OpenCart Adaptation | Preserve visual truth |
| 12 | Decision Rule | Agent decision framework |
| 13 | Acceptance Test | Pass/fail criteria |
| 14 | Short Identity Label | Tom Modern Design |

---

## Contents

- `SKILL.md` — ready-to-use skill file
- `tom-modern-html-style-rule.md` — expanded reference and system instruction
- `components/premium-token-card.md` — token/code card component spec
- `components/premium-code-window.md` — code display component spec

---

## Usage

1. Copy `SKILL.md` into your agent's skill directory
2. Or reference `tom-modern-html-style-rule.md` as a system instruction
3. When the user says `современный дизайн`, the agent creates HTML in this style
4. For specific components, reference the files in `components/`
