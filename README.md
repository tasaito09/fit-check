# FIT CHECK

A browser-based fitting room that compares clothing measurements against a reference garment and draws an approximate proportion overlay.

## Run locally

No npm dependencies or build step. With Python installed, from the repository folder:

```sh
python -m http.server 8000 --directory dist
```

On Windows, `py -m http.server 8000 --directory dist` also works.
Open http://localhost:8000 in your browser.
You can also use VS Code's Live Server extension to serve `dist/index.html`.

## Source map

- `dist/index.html`: page structure, styles, responsive layout, and profile dialog.
- `dist/app.js`: measurements, fit comparisons, SVG silhouette, profile editing, and browser-local wardrobe storage.
- `.openai/hosting.json`: configuration for the existing private ChatGPT Site; not required to run locally.

Despite the folder name, `dist/` contains the editable source. There is no generated build output.

## GitHub later

This download includes a real `.git` repository with commit history, on branch `main`, and no configured remote or credentials.
Create an empty GitHub repository (without a README, license, or gitignore), then run from this folder, replacing YOUR_USERNAME:

```sh
git remote add origin https://github.com/YOUR_USERNAME/fit-check.git
git push -u origin main
```

For further edits:

```sh
git add .
git commit -m "Describe the change"
git push
```

Authenticate with your own GitHub account when prompted. GitHub hosting and the private ChatGPT Site are separate; pushing to GitHub does not automatically update the Site.

## Checks

```sh
node --check dist/app.js
```

Manually verify live measurement changes, reference overlay, profile updates, and saving/reopening comparisons. Those flows were checked in the initial browser preview.

## Current scope

- Tops and jackets, measured flat in centimeters.
- Deterministic measurement comparisons and heuristic fit descriptions.
- Approximate 2D silhouette; no fabric physics, photo generation, or image uploads.
- LocalStorage persistence per browser and origin; no server database or cross-device sync.
- Starter body and garment measurements are examples; replace them with real measurements.
