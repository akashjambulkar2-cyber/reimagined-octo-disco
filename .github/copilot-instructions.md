# GitHub Copilot Instructions for testPDF

- This repository is a small static frontend project comprising two standalone HTML apps.
- There is no build tool, package manager, or test framework in the repository.
- Keep changes self-contained in the HTML files: `log-anomaly-analyzer.html` and `notepad.html`.

## Key application patterns

- `log-anomaly-analyzer.html`
  - Single-page UI with inline `<style>` and `<script>` only.
  - Uses DOM state via `data-type` attributes and active tab class toggling.
  - The live counter logic is entirely client-side and driven by textarea input events.
  - There is no backend or API integration; all behavior is in-browser.

- `notepad.html`
  - Browser-only text editor with `localStorage` persistence.
  - File open/save uses the File API and `Blob` download anchor.
  - Cursor position and word/character stats are computed in-page.

## What to avoid

- Do not introduce frameworks, transpilation, or bundlers unless explicitly requested.
- Avoid moving inline styles/scripts into external files unless the user asks for a refactor.
- Do not assume server-side behavior or backend APIs exist.

## Recommended dev workflow

- Edit the target HTML file directly.
- Preview changes in a browser to verify UI updates and JavaScript behavior.
- Preserve the existing inline structure and the simple dependency model.

## Notes for future maintainers

- If new features are added, keep the app architecture consistent: self-contained HTML with inline CSS/JS.
- If the project grows, prefer adding a real project structure only after the user approves a migration.
