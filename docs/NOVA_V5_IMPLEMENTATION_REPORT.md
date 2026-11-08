# NOVA DETAIL V5 — Implementation report
**Date:** 08 November 2026
**Status:** V5 alpha implemented and tested; V4 production remains live and unchanged.

## Live links
- V5 preview: https://kreamkilah.github.io/krm-digital-showcase/nova-v5-preview/
- V4 production: https://kreamkilah.github.io/nova-detail-demo-2026/
- Source branch: https://github.com/KreamKilah/nova-detail-demo-2026/tree/nova-v5
- QA: https://github.com/KreamKilah/krm-digital-showcase/actions/runs/42518635782

## Completed
- Obsidian/champagne visual refresh.
- Hero typography “CRAFTED IN LIGHT — DRIVEN BY DETAIL”.
- Original locally hosted studio hero (preserved).
- 2 additional original studio photographs (macro headlight and dark leather interior); permanent optimized WebP files at /assets/v5-macro.webp and /assets/v5-interior.webp.
- GSAP 3.15.0 and ScrollTrigger cinematic entry and scroll-based motion, reduced-motion compatible.
- Three-chapter synchronized visual story (silhouette / detail / feeling); responsive sticky image on mobile.
- Service copy refinement, richer color grading, menu improvements, existing lighting toggle, before/after simulation, fullscreen photo gallery retained.
- Mobile overflow issue identified via Playwright and fixed by art-directed responsive typography.
- Sticky mobile scene counter synchronization fixed and regression-tested.

## Automated browser checks
Playwright (Chromium):
- 390 px mobile: PASS; document overflow 0 px; hero visible and correctly framed; mobile menu, lighting toggle, before/after slider, gallery modal and chapter-02 scene synchronization passed.
- 1440 px desktop: PASS; document overflow 0 px; hero and story visible; lighting, slider, gallery and chapter-02 scene synchronization passed.
- No JavaScript page errors reported during these tests.
- Screenshots and JSON test report available as GitHub Actions artifact `nova-v5-visual-qa` (short retention).

## Honesty & limitations
- The brand is entirely fictitious, not a real detailing company.
- Before/after is a **color/brightness simulation of the same photo**, not a real result.
- Some gallery/service images still use Pexels. Do not claim all images are original.
- Does not include genuine bookings, customer reviews or contact collection.
- GSAP is currently loaded from a pinned CDN version with a CSS/JS fallback.
- Mobile/desktop smoke tests are not comprehensive performance, accessibility, network or cross-browser audits.
- V4 not yet replaced; do not treat alpha as production-ready commercial client deployment.
- The one-time import workflow was removed after importing assets. Repository secrets for the source URLs may remain until deleted with account-owner verification.

## Next design/quality steps
1. Generate/replace remaining stock photographs with a coherent custom original set (under an explicit credits budget).
2. Profile and optimize all image delivery, LCP, INP and CLS on actual mobile devices.
3. Review contrast, keyboard navigation and accessibility beyond smoke tests.
4. Tune chapter transitions, gallery design and copy after visual feedback.
5. Promote to `main` only when the user approves V5 after review.

**No EUR spent from the 50 EUR challenge capital; two new Runway images consumed 40 of the workspace's available credits.**
