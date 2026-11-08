# NOVA DETAIL V5.2 — CINEMATIC SIGNATURE
Date: 08-11-2026
Status: preview complete and QA passing; NOT promoted to production.

## Live links
- **V5.2 preview:** https://kreamkilah.github.io/krm-digital-showcase/nova-v52-preview/
- **Source branch:** https://github.com/KreamKilah/nova-detail-demo-2026/tree/nova-v52
- **Previous V5.1 preview:** https://kreamkilah.github.io/krm-digital-showcase/nova-v5-preview/
- **V4 public website:** https://kreamkilah.github.io/nova-detail-demo-2026/
- **Passing QA run:** https://github.com/KreamKilah/krm-digital-showcase/actions/runs/42522113989

## Changes completed
1. Cinematic Obsidian/Champagne polish: more consistent contrast and lights, premium CTA glints, subtler dark overlays, cleaner header and footer.
2. Image-mask reveals on desktop (7 panels), created only with GSAP available on capable pointer devices. Mobile and reduced-motion environments avoid heavy masks.
3. Five editorial animated lines connecting principal section headings and scroll progress through the narrative.
4. Refined signature story with animated active chapter rule and original image crossfade (previous image logic maintained).
5. NEW interactive Light Lab: original coating concept photo, two light grades on the same image, draggable slider, percentage feedback, reset button, accessible labels. Explicit disclaimer that this is a *digital lighting simulation, not a real detailing result*.
6. Reused existing original locally hosted WebP photography, no new Runway generation or paid assets.
7. Removed redundant stock background assets, fixed malformed Open Graph preview image URL, reused the locally cached original hero for closing CTA.

## QA evidence (Chromium/Playwright)
Workflow run `42522113989`, all checks **PASS**:
- Widths: **360**, **390**, **768**, **1440** pixels.
- No horizontal document overflow in any tested width.
- Hero, nav, responsive mobile menu, lighting toggle, original assets, story and scene counter synchronization.
- Light Lab slider updates style and numeric value and resets to 50%.
- Fullscreen gallery opens and closes, no page JavaScript errors in tested flows.
- Separate **normal-motion desktop** test passed: GSAP **3.15.0** loaded, **five** editorial rules and **seven** desktop photo-mask transitions activated; no overflow.
- Screenshot ZIP available as artifact `nova-v52-visual-report` on QA run.

## Limits
- Automated browser checks are not a full cross-browser/device matrix; physical phones not tested.
- Core Web Vitals/Lighthouse performance and accessibility scoring not yet measured. Avoid claiming quantified performance improvements beyond removing redundant background image requests.
- Some illustrative stock photo references or external resource credits may remain; all visuals must be licensed appropriately.
- The brand and service are fictional; no invented real bookings, customer ratings, real polishing results or client association.
- No commercial deployment: legal/privacy/business registration work postponed until appropriate.
- Some original image import temporary GitHub Actions repository secrets from earlier phases may still exist; owner verification is required to delete them. One-time import workflows have been removed.

## Financial status
Challenge cash: **50 EUR still intact; 0 EUR spent in V5.2**.
No new creative generation credits used in this phase.

**Promotion policy:** V5.2 branch is a preview. Preserve V4 and V5.1 until the user reviews V5.2 and explicitly opts to promote it.
