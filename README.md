
# Aurora Nav — Modern CSS‑Only Menu (HTML + CSS)

Sticky glass header with gradient underlines, dropdowns via `<details>`, and a mobile hamburger — no JavaScript required.

## Structure
```text
aurora-nav/
├─ index.html
└─ style.css
```

## Quick Start
1. Save the HTML as `index.html` and the CSS as `style.css`.
2. Ensure the stylesheet is linked in `<head>`:
```html
<link rel="stylesheet" href="style.css" />
```
3. Open `index.html` in your browser.

## How it works
- **Glass header:** `.header-bar` uses `backdrop-filter: var(--glass)` and a translucent `--surface`.
- **Active/hover underline:** `::after` gradient scales from 0 → 1 on links and summaries.
- **Dropdowns:** pure CSS using `<details><summary>…</summary><ul class="dropdown">…`.
- **Mobile nav:** a hidden checkbox (`#nav-toggle`) + `.hamburger` controls `.nav` max‑height at `< 900px`.
- **Responsive grid:** cards collapse 4 → 2 → 1 columns.
- **Dark mode:** color tokens switch with `prefers-color-scheme: dark`.

## Customize
- **Brand palette:** change `--primary`, `--accent` in `:root`.
- **Radius & shadows:** tweak `--radius`, `--shadow-*`.
- **Max width:** set `--maxw`.
- **Breakpoint:** adjust `@media (max-width: 900px)` for hamburger behavior.

## Accessibility notes
- Current page uses `aria-current="page"` on the active link.
- `summary` is focusable; gradients also show on `:focus-visible`.
- Hamburger has `aria-label="Toggle navigation"` and is tied to `#nav-toggle` via `for`.

## Troubleshooting
- **Hamburger not working?** Confirm `id="nav-toggle"` matches the label's `for` and the sibling selectors (`~ .nav`).
- **Blur missing?** `backdrop-filter` needs browser support; provide solid fallbacks if necessary.
- **Dropdown position issues?** `.dropdown` is absolutely positioned on desktop; it becomes static inside the mobile panel.

