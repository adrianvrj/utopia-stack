### UI design

**You own the look. Direction, then one implementer, then polish.** For landings, marketing sites, portfolios, product shells, redesigns, "make it look good", polish, or image-first builds. The work is the interface.

Do not match Feature (new behavior from a named data shape; incidental UI stays there), Prototype (throwaway sketch to decide), or Visual parity (make X match Y exactly). If both Feature and UI design match, Feature wins when a data shape is being introduced or changed; UI design otherwise.

These skills all want to implement. Assign one job each. Do not load two implementers on the same path.

- **design-taste-frontend** — brief inference, one-line Design Read, dial inference. Section 0 through 1.A. Stop before 1.B. Never implements.
- **high-end-visual-design** — apply bans and type/spacing rules only. Do not generate a second implementation.
- **apple-design** — extra constraint bar only when the read is Apple-y, gesture, or materials.
- **redesign-existing-projects** — scan / diagnose checklist on an existing UI. No greenfield rewrite.
- **imagegen-frontend-web** — one horizontal image per section. Marketing / landing / portfolio only.
- **image-to-code** — analyze those comps, then implement from them. Only after comps exist.
- **impeccable** — default implementer (`craft`) and later polish (`polish` / `audit`). Product UI and any code-first path. Resolve this skill's root as the directory that contains its `SKILL.md`. Run `node <skill-root>/scripts/<file>.mjs`. Do not require `live` or `hooks`.
- **emil-design-eng** — after code exists: Before/After review of components and motion. Skip its idle "I'm ready" greeting.
- **gsap-core** — motion when animation is in scope. Then **gsap-react** on React/Next, **gsap-scrolltrigger** for scroll, **gsap-timeline** for sequenced motion.

1. Classify the surface: marketing / landing / portfolio, product UI, or existing upgrade. Read **design-taste-frontend** section 0 through 1.A. Stop before 1.B. State the Design Read in one line (page kind, audience, vibe, system) and the three dials. Load **high-end-visual-design** for bans and type/spacing only; do not generate a second implementation. Load **apple-design** only if the read is Apple-y; otherwise `apple-design skipped: read is not Apple-y`. Load **redesign-existing-projects** only for an existing-app upgrade; otherwise `redesign-existing-projects skipped: not an existing upgrade`.
2. Pick one path. Write `skip: <reason>` on the two unused ones.
   - **Image-first.** Marketing / landing / portfolio, image generation is available, and the user did not say "just code it". Run **imagegen-frontend-web** (one image per section), then **image-to-code**.
   - **Code-first.** Product UI, or the user said "just code it", or image generation is unavailable. Run **impeccable** `craft`. If `context.mjs` reports `NO_PRODUCT_MD`, skip impeccable init. The Design Read is enough. Do not block a landing page on writing `PRODUCT.md`.
   - **Existing upgrade.** Run the **redesign-existing-projects** audit, then **impeccable** on the existing stack. No greenfield rewrite.
3. Motion if in scope: **gsap-core**, then the matching sibling. Otherwise `skip: no motion`.
4. Polish: **impeccable** `polish` / `audit`, then **emil-design-eng** review table.
5. Verify in the browser on the real surface. Prefer the matching control skill (`control-ui` for web). If `control-ui` is missing, drive the surface with the available browser tools, or ask in plain words. Desktop, and a mobile viewport if layout changed. **prove-it-works**. A screenshot of first paint is not a pass.
6. Run **Opening a PR**. If `/deslop` is missing, ask for the same outcome in plain words. If the workspace has no git remote or the user said not to open a PR, `skip: no git / not asked`.

**Reply:** the Design Read, which path you took and why, what you built, the polish findings you accepted, open decisions. Screenshots of the verified surface.
