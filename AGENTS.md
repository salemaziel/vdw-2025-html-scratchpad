# Repository Guidelines

## Project Structure & Module Organization
- Root contains static HTML prototypes for Via Del Web landing pages (e.g., `index.html`, dated variants like `via-del-web-redesign-v4-2025-12-10.html`).
- Shared assets live in `assets/images/`; keep new images here and reference with relative paths (`assets/images/...`).
- No build pipeline at present—files are served directly; keep third-party embeds lightweight and self-contained.

## Build, Test, and Development Commands
- Local preview (default): `python -m http.server 8000` from repo root, then browse `http://localhost:8000/index.html` or any variant file.
- Live reload option: if available, run `npx live-server --port=8000 .` for hot refresh while editing HTML/CSS.
- Asset optimization (optional): `npx imagemin assets/images/* --out-dir=assets/images` before committing new images.

## Coding Style & Naming Conventions
- HTML: 2-space indentation; prefer semantic tags (`header`, `section`, `main`, `footer`) over extra `div`s.
- CSS/inline styles: group related rules, keep color variables consistent; use kebab-case class names (e.g., `hero-cta`, `primary-button`).
- File naming: follow existing pattern `via-del-web-<descriptor>-v<rev>-YYYY-MM-DD.html` for new iterations; avoid spaces.
- Assets: export web-friendly PNG/JPEG/WebP at reasonable sizes; name images with lowercase-kebab descriptors (e.g., `services-webdesign-04.png`).

## Testing Guidelines
- No automated test suite; validate pages with `npx htmlhint *.html` (install `htmlhint` once via `npm install -g htmlhint`).
- Manually verify responsive breakpoints at 320px, 768px, and 1280px widths; check Lighthouse for performance and accessibility before shipping.
- Ensure all image alt attributes and meta tags (title, description, OG tags) are present on new pages.

## Commit & Pull Request Guidelines
- Use concise, imperative commit subjects; prefer Conventional Commit scopes when clear (e.g., `feat: add v5 landing layout`, `chore: compress hero assets`).
- Include PR summary of key visual or copy changes, list affected HTML files, and attach before/after screenshots if UI changed.
- Link related issue/ticket; note any manual checks performed (HTMLHint, Lighthouse). Avoid committing large unused assets or node_modules.

## Security & Configuration Tips
- Do not embed production secrets or analytics keys; keep API tokens out of the repo.
- Host fonts locally when possible; minimize external script usage to reduce privacy and performance risks.
- When adding new images, ensure licensing is compatible and credit is recorded where required.
