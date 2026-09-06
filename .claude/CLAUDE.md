# charleslin.dev — Claude Code context

## NEVER CHANGE
- **Domain** `charleslin.dev` — printed as QR code on 25 physical PCBs already ordered
- **`CNAME` file** in repo root — must always contain exactly `charleslin.dev`
- **DNS records** at Porkbun (A records → GitHub IPs, www CNAME → clin1146.github.io)
- **Repo must stay public** — GitHub Pages free tier requirement
- **HTTPS must stay working** — `.dev` is HSTS-preloaded, HTTP is refused by browsers

## Hosting
- GitHub Pages: `github.com/clin1146/charleslin.dev`, branch `main`, root `/`
- Custom domain set in Pages settings, HTTPS enforced
- Live at `https://charleslin.dev`

## Stack
Plain HTML — no framework, no build step, no dependencies. Deploys are instant on push.
- If adding a build step: Jekyll works natively on GitHub Pages. Anything else (Astro, Hugo, Eleventy) needs a GitHub Actions workflow.
- **Given deadlines, stay with plain HTML unless there's a strong reason.**

## Current design (as of 2026-09-06)
- **Color scheme:** Illini Blue `#13294B` background, `#0d1f38` for alternating sections, Illini Orange `#FF5F05` for all accents/links. White/light-grey body text.
- **Layout reference:** `amierulhakeem.dev` — sticky nav, full-viewport hero, full-width alternating feature blocks. Colors and code are original.
- **Structure:**
  - Sticky nav: "Charles Lin" logo left, About / Projects / Résumé button right
  - Hero: eyebrow label, large name, tagline, two CTA buttons (View Projects + Download Résumé)
  - About Me section (placeholder text — needs real copy)
  - Engineering Projects: three alternating image/text blocks
    1. BSPD (image left)
    2. Embedded Systems Project — Line-Following Buggy (image right)
    3. Dual Gas-Sensing Platform for Peatland GHG Research (image left)
  - Footer: GitHub / LinkedIn / email links
- **Responsive:** single-column below 720 px; nav collapses to Résumé button only on mobile
- **Images:** placeholder `<div>` boxes in each project block; real images go in `/assets/` — swap comments are in the HTML

## Tone
Understated, technical, no marketing language. Written for engineers handed a physical card.

## Files
```
CNAME                    one line: charleslin.dev  ← never touch
index.html               the whole site, self-contained
Charles_Lin_Resume.pdf   linked from nav and hero buttons
.claude/CLAUDE.md        this file
```
Note: resume is `Charles_Lin_Resume.pdf` (not `resume.pdf`). Both nav and hero buttons already point to the correct filename.

## Email
`charles@charleslin.dev` → `charlielin931114@gmail.com` (Porkbun forwarding)

## GitHub account
Renamed `Charlyeeyee` → `clin1146`. Apex domain unaffected. GitHub link in index.html is already `github.com/clin1146`.

## Project background
PCB business card: playable 2-player Connect 4, 85×55 mm.
- STM32F042G6U6 (Cortex-M0, 48 MHz, 32 KB flash, 6 KB RAM)
- 42× XL-2020RGBC RGB LEDs (WS2812B), 7×6 grid
- Capacitive touch via STM32 TSC (no mechanical buttons)
- Mid-mount USB-C flush with board surface
- 4-layer, black soldermask, ENIG gold, epoxy vias
- Bare-metal C firmware, no HAL, direct register access

**Attribution:** design referenced from Amierul Hakeem (`amierulhakeem.dev`), permission to publish obtained. Needs a credit on the site (not yet added).

---

## TODO

### Content (placeholders to fill)
- [ ] **About Me** — write real first-person bio (short, technical, understated)
- [ ] **BSPD** — one-line description + project image → `/assets/bspd.jpg`
- [ ] **Line-Following Buggy** — one-line description + project image → `/assets/buggy.jpg`
- [ ] **Gas-Sensing Platform** — one-line description + project image → `/assets/gas-sensor.jpg`
- [ ] **"Read More" links** — currently `href="#"`; wire up to actual project pages or anchors
- [ ] **Amierul Hakeem attribution** — add credit somewhere on the site (footer or about section)

### Infrastructure
- [ ] **`www` TLS cert error** (`ERR_CERT_COMMON_NAME_INVALID`) — re-issue by: Settings → Pages → delete custom domain → Save → re-enter `charleslin.dev` → Save. Wait 15–60 min. Not blocking (QR/links use apex domain).

### Nice to have
- [ ] Individual project detail pages (or expanded sections) once content is ready
- [ ] Hero tagline — currently generic; could be more specific once project context is clearer
