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

## Style / tone
Dark `#0d0d0f` background, gold `#c9a227` accent — matches physical PCB (black soldermask, ENIG gold).
Connect 4 motif: four filled gold discs + three empty. Written for engineers handed a physical card. Understated, technical, no marketing language.

## Outstanding items (from handoff)
1. **GitHub link** in `index.html` still reads `github.com/charlyeeyee` → change to `https://github.com/clin1146`
2. **`www` TLS cert error** (`ERR_CERT_COMMON_NAME_INVALID`) — fix: Settings → Pages → delete custom domain → Save → re-enter `charleslin.dev` → Save. Wait 15–60 min. Not blocking (QR/links use apex domain).
3. **Email link** — consider showing `charles@charleslin.dev` as link text instead of just "Email" (mailto: is silent on machines with no mail client)
4. **Verify `resume.pdf`** uploaded and download button works (handoff noted `resume.pdf` but repo currently has `Charles_Lin_Resume.pdf` — confirm filename matches `index.html` link)

## Email
`charles@charleslin.dev` → `charlielin931114@gmail.com` (Porkbun forwarding)

## Project background
PCB business card: playable 2-player Connect 4, 85×55 mm.
- STM32F042G6U6 (Cortex-M0, 48 MHz, 32 KB flash, 6 KB RAM)
- 42× XL-2020RGBC RGB LEDs (WS2812B), 7×6 grid
- Capacitive touch via STM32 TSC (no mechanical buttons)
- Mid-mount USB-C flush with board surface
- 4-layer, black soldermask, ENIG gold, epoxy vias
- Bare-metal C firmware, no HAL, direct register access

**Attribution:** design referenced from Amierul Hakeem (`amierulhakeem.dev`), permission to publish obtained. Credit on site.

## GitHub account
Renamed `Charlyeeyee` → `clin1146`. Apex domain unaffected (A records). www CNAME already updated.
