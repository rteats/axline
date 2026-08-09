# AXLINE AGENCY landing — local launch on NixOS

The landing is fully static: **HTML + compiled Tailwind CSS**, no JavaScript and no build step is required.

## Fastest option

```bash
cd axline_landing
xdg-open index.html
```

This opens the site directly from the filesystem in your default browser.

## Recommended option: local HTTP server

If Python 3 is already installed:

```bash
cd axline_landing
python3 -m http.server 8080
```

Then open:

```text
http://127.0.0.1:8080
```

If Python is not installed globally on NixOS, run it temporarily through Nix:

```bash
cd axline_landing
nix shell nixpkgs#python3 -c python3 -m http.server 8080
```

For systems where you use the classic `nix-shell` command:

```bash
cd axline_landing
nix-shell -p python3 --run "python3 -m http.server 8080"
```

## Files

- `index.html` — page markup, Tailwind utility classes, inline SVG icons.
- `styles.css` — compiled Tailwind CSS 4.1.10; no browser-side JS is used.
- `assets/` — visual fragments used in the hero, case cards, and team cards.

The page has no functional forms or scripts by design; buttons/links are visual anchors/placeholders.
