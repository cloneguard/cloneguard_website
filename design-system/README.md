# Vendored design system (CSS layer only)

This folder is a copy of the token/base CSS from the CloneGuard Design System
(source: `~/Downloads/CloneGuard Design System/`), vendored into the site repo
so the live site doesn't depend on a file in the local Downloads folder.

Files here: `styles.css` (entry point, imports everything below) and `tokens/*.css`
(colors, typography, spacing, effects, base, fonts).

This is CSS only — the source system's `components/*.jsx` and `ui_kits/` are
React reference implementations for prototyping in that tool. This site is
static HTML/CSS, so component visuals (buttons, cards, badges, verification
card) are re-implemented as plain CSS classes in the homepage's `<style>`
block, built to match each component's spec 1:1. They will NOT auto-update
if a `.jsx` file changes — only token changes (colors/spacing/type/effects)
propagate automatically through this folder.

## Re-syncing after the source design system changes
Re-run this from a shell with access to both folders:

```
cp "~/Downloads/CloneGuard Design System/styles.css" design-system/styles.css
cp "~/Downloads/CloneGuard Design System/tokens/"*.css design-system/tokens/
```

If a component's visual spec changes (e.g. Button hover behavior, radius),
re-check `components/*/*.jsx` and `*.prompt.md` in the source folder and
update the matching CSS class by hand — that step is manual by design.
