# StoryCare — Brand & Design System

This is the design source of truth for the StoryCare marketing site (storycare.health). All code changes should follow these patterns.

---

## Brand Identity

**Product:** StoryCare — a therapist-led mental health treatment that transforms personal narratives into images, music, and video to support progress and clinical recovery.

**Positioning:** Digital Narrative Therapy. Clinical tool, not a consumer app. The therapist is always in control.

**Voice & Tone:**
- Clinical authority paired with human empathy
- Direct, concrete, never vague or abstract
- Transparent about product stage ("in clinical evaluation")
- Patient stories use emotional, poetic language; product descriptions stay precise
- Avoid: jargon overload, hype language, consumer-app framing

**Key phrases:** "Therapy beyond words," "therapist-led," "clinician-controlled," "the therapist controls"

---

## Color System

### Core Palette

| Token | Value | Usage |
|-------|-------|-------|
| `--accent` | `#9810FA` | Brand purple. Buttons, labels, icons, links |
| `--bg-dark` | `#FFFFFF` | Page background |
| `--bg-card` | `#F5F5F7` | Card/block backgrounds |
| `--text-primary` | `#1A1A2E` | Headings, body text |
| `--text-secondary` | `rgba(26, 26, 46, 0.65)` | Subtitles, descriptions, labels |
| `--text-tertiary` | `rgba(26, 26, 46, 0.4)` | Timestamps, metadata, footer links |
| `--accent-glow` | `rgba(152, 16, 250, 0.15)` | Subtle purple backgrounds, glows |
| `--border` | `rgba(0, 0, 0, 0.08)` | Dividers, card borders |

### Dark Theme (phone/therapist mockups only)

| Token | Value |
|-------|-------|
| `--text-primary` | `#F5F5F7` |
| `--text-secondary` | `rgba(245, 245, 247, 0.7)` |
| `--border` | `rgba(255, 255, 255, 0.06)` |
| Background | `#1A1A2E` |

### Accent Opacity Scale

- 8% — badge backgrounds, subtle tints
- 10–12% — AI tags, hover states
- 15% — glow effects, accent-glow
- 25% — gradient endpoints
- 50% — scroll hint, medium emphasis
- 60% — active waveform bars
- 100% — buttons, links, icons

### Key Gradients

- **Hero:** `linear-gradient(180deg, #FFFFFF 0%, #F3EAFF 100%)` — white to soft lavender
- **Brand gradient:** `linear-gradient(135deg, #9810FA, #6B0FBF)` — purple to deep purple
- **Fade masks:** `linear-gradient(to right, #FAF8FF, transparent)` — carousel edges

---

## Typography

### Font Families

- **Headings:** `'Playfair Display', Georgia, serif` — elegant, clinical weight
- **Body:** `'Inter', -apple-system, BlinkMacSystemFont, sans-serif` — clean, readable
- **Monospace:** `monospace` — timestamps, audio durations only

### Scale (responsive with clamp)

| Element | Size | Weight |
|---------|------|--------|
| Hero brand | `clamp(2.8rem, 6vw, 4.5rem)` | 700 |
| Hero h1 | `clamp(2.2rem, 5vw, 3.8rem)` | 600 |
| Section title | `clamp(1.8rem, 4vw, 2.8rem)` | 600 |
| Section subtitle | `1.05rem` | 400 |
| Body text | `0.9rem–1rem` | 400 |
| Labels/badges | `0.75rem–0.8rem` | 600, uppercase |
| Small text | `0.65rem` | 400–500 |

### Conventions

- Headings: Playfair Display, always. Line-height 1.15–1.2.
- Body: Inter, line-height 1.6–1.7 for readability.
- Labels: uppercase, letter-spacing `0.04em–0.15em`, font-weight 600.
- Never use bold (700) for body text. Use font-weight 500 for emphasis.

---

## Spacing

### Section Rhythm

- Section padding: `6rem 2rem` (desktop), `4rem 1.25rem` (mobile)
- Between sections: consistent 6rem vertical breathing room
- Content max-width varies by section (700px–1100px), centered

### Base Units

- Tight: `0.25rem–0.5rem` (inline gaps, icon-to-text)
- Standard: `1rem` (form groups, card padding)
- Comfortable: `1.5rem–2rem` (section internal spacing)
- Generous: `3rem–4rem` (grid gaps, section headers to content)

---

## Components

### Buttons

**Primary (`.btn-primary`)**
- Background: `--accent`, color: white
- Padding: `0.75rem 2rem`, border-radius: `8px`
- Hover: `brightness(1.15)`, `translateY(-1px)`
- Font: 0.95rem, weight 500

**Ghost (`.btn-ghost`)**
- Transparent background, `--text-secondary` color
- Same padding, no border
- Hover: color shifts to `--text-primary`

**Sign-in (`.btn-signin`)**
- Outline style: accent border, accent text
- Padding: `0.4rem 1rem`, border-radius: `6px`
- Hover: fills with accent, text goes white

### Cards

**Why blocks** — `--bg-card` background, `3px left border` in accent, `1.75rem` padding
**Story cards** — white background, image + figcaption, `box-shadow: 0 2px 12px rgba(0,0,0,0.1)`, 280px wide
**Feature cards** — `--bg-card` with 1px border, `border-radius: 12px`, `1rem` padding

### FAQ Accordion

- Toggle via `.open` class on `.faq-item`
- Answer hidden with `max-height: 0; overflow: hidden`, animates to `500px`
- Chevron rotates 45deg on open
- Pure CSS/inline JS — no library

### Forms

- Input/textarea/select: white background, `1px solid rgba(0,0,0,0.12)` border, `8px` radius
- Focus: border-color changes to `--accent`
- Labels: `0.8rem`, `--text-secondary`
- Submit: full-width `.btn-primary`
- Submits to JotForm (HIPAA): `https://hipaa.jotform.com/submit/260444105747051`

### Phone Mockup

- 280px wide, `#1A1A2E` background, `32px` border-radius
- Dark theme variables override inside
- Notch: 100px wide, 24px tall, `#0A0A0F`
- Deep shadow: `0 20px 60px rgba(0,0,0,0.5)`

---

## Layout & Responsive

### Breakpoints

| Breakpoint | Target | Key changes |
|------------|--------|-------------|
| `900px` | Large tablet | Story page + clinical grid go single-column |
| `768px` | Tablet | Hamburger nav, steps stack vertical, section padding shrinks |
| `600px` | Mobile | Hero `min-height: auto`, CTAs stack, scroll hint hidden |
| `520px` | Small mobile | Feature grid single-column, trust bar tighter |

### Navigation

- Fixed, `z-index: 100`
- `rgba(255, 255, 255, 0.85)` background with `backdrop-filter: blur(20px)`
- Mobile: hamburger toggle, links drop down as column

### Content Widths

- Hero content: `750px`
- Main sections: `1100px`
- FAQ / contact: `700px`
- Contact form: `500px`
- Legal pages: `700px`

---

## Animation & Interaction

### Scroll Fade-in

- `.fade-in` elements: `opacity: 0 → 1`, `translateY(24px → 0)`, `0.6s ease`
- Children (`.fade-in-child`): same but `16px` and `0.5s`, staggered `0.1s` delay
- Triggered by IntersectionObserver at `threshold: 0.15`
- Guarded by `.js-fade-ready` class to prevent flash of unstyled content

### Scroll Hint

- Bouncing chevron at hero bottom, `opacity: 0.5`, fades out after 80px scroll
- Hidden on mobile (`max-width: 600px`)

### Transitions

- Fast (0.2s): color, opacity, border-color — hover/focus states
- Medium (0.3s): transforms, box-shadow, max-height — accordion, card interactions
- Slow (0.5–0.6s): fade-in — scroll-triggered reveals

---

## Accessibility

- Focus: `2px solid var(--accent)`, `2px offset` on all interactive elements
- Touch targets: minimum `44px` on mobile (nav, FAQ, buttons)
- Semantic HTML: `<nav>`, `<main>`, `<section>`, `<figure>/<figcaption>`, `<footer>`
- `scroll-padding-top: 70px` to account for fixed nav
- All images have descriptive `alt` text
- `loading="lazy"` on below-fold images
- `aria-label` on nav, `aria-hidden` on decorative elements

---

## File Structure

```
/
  index.html        — Main landing page (all styles inline in <style>)
  privacy.html      — Privacy policy (shares same design tokens)
  terms.html        — Terms of service (shares same design tokens)
  vercel.json       — Deployment config with cache headers
  images/
    logo.png        — Brand mark (used at 36px in nav, 24px in footer)
    favicon.png     — Browser tab icon
    apple-touch-icon.png
    og-image.png    — Social sharing preview
    hero-bg.jpg     — Background image (gradient used instead)
    phone-mockup.jpg — Video thumbnail in phone demo
    story-1–6.jpg   — Patient story carousel images
```

## Project Context

**StoryCare** is built by Entryway Health, in collaboration with Sage Health. It is currently in clinical evaluation — presenting at SIRS 2026 in Florence, Italy.

**Related services:**
- **App:** app.storycare.health (the therapist/patient platform — Sign In button links here)
- **Landing site:** storycare.health (this repo)
- **GitHub org:** nh-entryway

---

## Deployment & Infrastructure

- **Hosted:** Vercel (storycare-home.vercel.app)
- **Domain:** storycare.health
- **Repo:** github.com/nh-entryway/storycare-home
- **Branch:** `main` (pushes auto-deploy to Vercel production)
- **Cache:** HTML pages set to `must-revalidate` via vercel.json — changes go live immediately

---

## Forms (JotForm — HIPAA)

All forms are on the HIPAA-compliant JotForm instance (`hipaa.jotform.com`).

### Contact Form (on landing page)

- **Form ID:** `260444105747051`
- **Title:** StoryCare — Get in Touch
- **Submit URL:** `https://hipaa.jotform.com/submit/260444105747051`

**Field mapping (HTML name → JotForm question):**

| HTML `name` attribute | JotForm field | Type |
|----------------------|---------------|------|
| `q2_fullName[first]` | Full Name | text |
| `q3_emailAddress` | Email Address | email |
| `q6_role` | Role | dropdown (Individual clinician, Clinical director / organization, Researcher, Other) |
| `q4_message` | Tell us about your setting or interest | textarea |

### Other JotForm Forms (related to the clinical trial)

| Form ID | Title |
|---------|-------|
| `260395639354062` | Storycare Trial — Self Signup |
| `260395343290053` | Storycare Trial — Clinician Enrollment |
| `260394968625067` | DNET — Exit Survey (Early Withdrawal) |
| `260395354421051` | DNET — End of Therapy Questionnaire |
| `260395228806058` | DNET — Beginning of Therapy Questionnaire |

---

## SEO & Social Sharing

- **Title:** StoryCare | Digital Narrative Therapy
- **Meta description:** "StoryCare is a clinician-guided digital therapeutic that turns what patients share in therapy into images, videos, and music they keep and build on between sessions."
- **OG image:** `images/og-image.png` (1200x630)
- **Twitter card:** summary_large_image

---

## Architecture Notes

- **Single-file approach.** All CSS is in a `<style>` block in `<head>`. All JS is in `<script>` blocks before `</body>`. No external CSS or JS files, no build step, no bundler.
- **No frameworks.** Pure HTML, CSS, vanilla JS. Keep it this way.
- **Google Fonts loaded via `<link>`.** Inter (300, 400, 500, 600) and Playfair Display (400, 500, 600, 700).
- **Legal pages** (privacy.html, terms.html) share the same design tokens and patterns but use a simpler layout with `.legal-content` container at 700px max-width.
- **Form submissions** use `fetch()` with `mode: 'no-cors'` — the form shows a success message optimistically. JotForm handles storage and notifications.

---

## Design Principles

1. **Clean over clever.** No decoration without purpose. White space is a feature.
2. **Clinical credibility first.** The design should feel like a serious health tool, not a startup landing page.
3. **Therapist audience.** Every word and visual should resonate with clinicians, not patients.
4. **Progressive disclosure.** Hero is simple; complexity reveals as you scroll.
5. **Light touch on animation.** Subtle fade-ins and transitions. No bouncing, sliding, or attention-grabbing effects (scroll hint is the one exception, kept minimal).
6. **Accessibility is non-negotiable.** Touch targets, focus states, semantic markup, lazy loading.
7. **Single-file simplicity.** All styles are inline. No build step, no CSS framework, no JS framework.
