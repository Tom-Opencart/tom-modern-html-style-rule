---
name: tom-modern-design
description: Use when the user asks for modern HTML design, uses the trigger phrase `современный дизайн`, or wants a standalone HTML page, landing page, promo page, HTML description, or OpenCart-bound visual reference in Tom's accepted modern editorial-technical style. This skill routes the task through the HTML-first modern-design workflow, avoids generic AI landing-page patterns, preserves OpenCart-native ergonomics when the target is an OpenCart admin or module UI, and requires desktop plus mobile verification before completion. The current trigger phrase is `современный дизайн`, but it may be changed by editing this skill.
---

# Tom Modern Design Skill

Use this skill when the user asks for:
- `современный дизайн`
- modern HTML
- a polished landing page
- an HTML description
- a promo page
- a visual HTML reference to adapt later into OpenCart

The current hard trigger phrase is:
- `современный дизайн`

This trigger can be changed later.

## Workflow

1. Determine whether the target is:
   - standalone HTML / landing / promo / description
   - OpenCart admin / OpenCart module UI
2. Prefer HTML-first execution unless the user explicitly requires direct template integration.
3. Build the result in Tom's accepted modern design family.
4. Avoid generic AI-generated landing-page patterns.
5. Verify both desktop and mobile before sign-off.

## Style Identity

The target style is:
- editorial + technical
- modern but restrained
- structured
- premium
- high-signal
- anti-generic

It is not just “Swiss Kinetic”.
It overlaps with Swiss discipline, editorial structure, and technical minimalism, but it is broader than any one of those labels.

## Hard Rules

### No AI Slop

Do not generate:
- generic centered startup heroes
- purple gradient defaults
- blob-based filler
- repetitive identical feature-card grids
- generic SaaS templates

If the page looks interchangeable with mass AI-generated landing pages, it fails.

### Typography Must Carry the Design

Prefer:
- Geist-like main typography
- Geist Mono-like micro-labels and technical notes
- strong hierarchy
- compact uppercase labels where useful
- controlled line length

### Layout Must Be Structured

Prefer:
- split layouts
- framed sections
- asymmetry where justified
- meaningful section rhythm
- contrast between quiet and dense areas

Avoid:
- one repetitive stack
- equal-width everything
- same card pattern in every section

### Color Must Be Restrained

Use:
- one primary accent
- mostly neutral supporting palette
- strong text contrast

Avoid:
- many accents
- uncontrolled neon
- dark mode by default unless explicitly requested

### Background Must Support Atmosphere

Prefer:
- technical grids
- structural lines
- quiet texture
- restrained depth

Avoid:
- empty flat background with no atmosphere
- background effects as the whole design idea

## Branching Rule

### Standalone HTML Branch

For landings, promo pages, and HTML descriptions:
- use the stronger visual language
- allow technical backgrounds, split heroes, demo blocks, and stronger composition

### OpenCart Branch

For OpenCart admin or module UIs:
- preserve OpenCart shell ergonomics
- preserve settings-page usability
- keep Bootstrap 3 friendly structure when needed
- apply modern design as an internal refinement layer, not a foreign dashboard redesign

## HTML Rules

Default scaffold:
- `index.html`
- `style.css`

Rules:
- semantic HTML
- real text, not lorem ipsum
- avoid inline styles
- use meaningful `id` values for important blocks
- keep code readable for later adaptation

## Motion Rule

Motion is optional and must be purposeful.

Prefer:
- restrained reveal animation
- subtle hover transitions
- lightweight structure-supporting motion

Avoid:
- decorative motion overload
- slow or distracting transitions

## Responsive Rule

Desktop and mobile verification are mandatory.

The result is incomplete if mobile has:
- cramped CTAs
- overlap
- broken hero composition
- unreadable text
- overflow
- weak spacing rhythm

## OpenCart Adaptation Rule

If this HTML will later be adapted into OpenCart:
- treat the HTML as the approved visual source of truth
- do not re-invent the style during adaptation
- adapt later into Twig/PHP/language files as a separate step

## Acceptance Test

The result passes only if:
- it does not look like generic AI-generated HTML
- it has clear hierarchy and structural rhythm
- typography feels intentional
- layout has composition
- accent use is restrained
- desktop and mobile both work
- it belongs to Tom's accepted `современный дизайн` family

## Reference

For the expanded version of this rule, read:
- `tom-modern-html-style-rule.md`
