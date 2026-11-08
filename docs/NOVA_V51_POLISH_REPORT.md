# NOVA DETAIL V5.1 — Cinematic Motion & Photography
Date: 2026-11-08
Status: Preview deployed and browser smoke-tested; V4 remains live and unchanged.

## Deliverables

- Preview: https://kreamkilah.github.io/krm-digital-showcase/nova-v5-preview/
- Branch: https://github.com/KreamKilah/nova-detail-demo-2026/tree/nova-v5
- V4 production: https://kreamkilah.github.io/nova-detail-demo-2026/
- QA workflow: https://github.com/KreamKilah/krm-digital-showcase/actions/runs/42519777235

### 1. Cinematic motion
- Rebuilt the GSAP opening timeline: more deliberate title choreography with subtle 3D line entrance, gold line and text, CTA reveal.
- Added scroll-triggered editorial reveal motion to services, gallery and section headings.
- Increased control of parallax and light movement while keeping fallback content visible if animations don't load.
- Simplified grading of hero, service images, gallery and final section; softened highlights and deepened obsidian tones.
- Preserved reduced-motion support, lighting toggle and story synchronization.

### 2. Coherent original photography
Five original digitally generated automotive concept assets now form the brand world:
- Existing hero: `assets/nova-hero.webp`
- Existing headlamp macro: `assets/v5-macro.webp`
- Existing cockpit: `assets/v5-interior.webp`
- New automotive polishing: `assets/v51-polish.webp`
- New water-beading protection scene: `assets/v51-coating.webp`

The new imagery replaced stock in polish/protection service cards, gallery and full-width visual statement.
The before/after slider continues using a Pexels photo as a declared visual filter simulation; it does **not** imply real client results.
All photography is concept art; it must not be passed off as real client work.
Image-import workflow was removed after importing assets. Some temporary source URL secrets still require owner verification to delete.

## QA

Playwright Chromium workflow run `42519777235`:
- At **390 px**: PASS, zero horizontal overflow, hero, story, controls, menu, slider and gallery smoke checks.
- At **1440 px**: PASS, zero horizontal overflow, same core smoke tests.
- No page JS errors reported in these tests.
- Screenshot artifact name: `nova-v5-visual-qa`.

These are functional smoke checks. They do not replace a performance audit (Lighthouse / LCP / INP / CLS), accessibility audit or tests on real physical devices.

## Outstanding
- Test multiple physical mobile devices and image readability across more screen sizes.
- Audit accessibility, color contrast, font loading, Lighthouse performance.
- Evaluate whether the before/after needs real consented example footage; do not fabricate client results.
- Fix privacy/legal operating readiness before a real commercial offering.
- Publish V5 to main only after deliberate approval.

## Budget
0 EUR spent from the 50 EUR challenge capital.
40 existing Runway workspace credits consumed for two new images; last observed workspace balance 25.
