# AGENTS.md

## What this repo is

Static **user-manual website** for the **Control** desktop app (a .NET 8.0 / WinForms tool for PAM Argentina: Ingresos, Inventario, Movimientos Bernafon). It is plain Markdown rendered by **Docsify** (loaded from CDN) and published via **GitHub Pages** from `main`.

There is **no build, lint, test, typecheck, or package manager**. The `.md` files *are* the site — edit and commit; GitHub Pages serves the result. Do not invent npm/CI commands.

## The app it documents

The **Control** app's source lives in a separate repo on this machine: `C:\Users\agusm\source\repos\Control` (not part of this repo). When writing or verifying UI descriptions, labels, and business rules, read that source rather than guessing:

- `UI/` — WinForms forms (`Frm*.cs` / `.Designer.cs` / `.resx`); the **`.resx` / `.Designer.cs` hold the literal Spanish UI strings** the manual must match.
- `Logic/` — business rules (comparison, Excel/PDF export, QR, printing).
- `Control.Tests/` — xUnit tests plus sample `.xls(x)` fixtures documenting real input formats.

## Structure

- `index.html` — Docsify bootstrap: theme, plugins, custom CSS, and the runtime version fetch. Home route is `README.md`.
- `_sidebar.md` — the sidebar navigation.
- `README.md`, `configuracion.md`, `ingresos.md`, `inventario.md`, `movimientos_bernafon.md`, `acerca_de.md` — the manual pages.
- `_media/` — screenshots/GIFs, grouped by module (`_media/Configuracion/`, `_media/Ingreso/`, `_media/Inventario/`, `_media/Movimiento/`); `_media/Pantalla_Principal.png` is at the root.
- `.nojekyll` — required so GitHub Pages serves underscore-prefixed assets (`_sidebar.md`, `_media/`). **Do not delete it.**

## Editing rules

- All user-facing content is **Spanish (es-AR)**. Match the existing voice.
- **A new page is unreachable until you add it to `_sidebar.md`** (with an emoji heading, matching the existing grouping style).
- Internal links: link to a page as `foo.md`, but link to a section as `page#slug` **without** `.md`, e.g. `configuracion#configuracion-por-linea`. Slugs are lowercase, hyphenated, accent-stripped. Note filenames use underscores (`movimientos_bernafon.md`) while anchors use hyphens — verify the target file actually exists.
- Alerts use the flexible-alerts blockquote syntax: `> [!TIP]`, `> [!INFO]`, `> [!WARNING]`.
- Reuse the custom component classes defined in `index.html` (`ad-hero`, `ad-chips`, `ad-chip`, `ad-grid`, `ad-card`, `ad-roadmap`, `ad-support`, `ad-pill`) rather than inventing new markup.
- Reference images with relative paths (`_media/Configuracion/Configuracion.png`). Missing screenshots are already marked with `<!-- PLACEHOLDER: ... -->` comments — keep that convention.
- Never hardcode the app version/date shown on `acerca_de.md`: `index.html` injects them at runtime from the GitHub releases API of `Control-PAM-Software/Control-PAM-Dist` (fallback value lives in `index.html`).
