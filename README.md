# Deploying to GitHub Pages

This is a fully static site (HTML + CSS + JS) — no database or backend needed.

## Folder structure
```
portfolio/
├── index.html
├── assets/
│   ├── photo.jpeg
│   ├── resume.pdf
│   └── projects/
│       ├── project-financial-statement-analysis.pdf
│       ├── project-corporate-finance-automobile.xlsx
│       ├── project-dcf-jk-tyre.pdf
│       ├── project-mutual-fund-dashboard.xlsx
│       └── project-statistical-analysis-nse.pdf
```

## Steps
1. Create a new GitHub repository (e.g. `pratibha-portfolio`).
2. Upload this entire folder's contents to the repo root (keep the `assets/` folder structure exactly as-is — the links in `index.html` are relative paths like `assets/resume.pdf`).
3. In the repo: **Settings → Pages → Source** → select the `main` branch and `/ (root)` folder → Save.
4. GitHub gives you a live URL, typically `https://<username>.github.io/<repo-name>/` — it can take a minute to go live.

## Behavior
- **Resume**: the Download Resume buttons use `download="Pratibha_Jain_Resume.pdf"` — clicking them saves the file directly, no new tab.
- **Projects**: each "View Project" opens the file in a new tab (`target="_blank"`, no `download` attribute) — no forced save dialog. PDFs render inline in the browser. The two Excel (`.xlsx`) projects will typically download instead of previewing, since browsers can't render Excel files inline — that's a browser limitation on a static site, not something the link controls. If you want those to open in-browser like the PDFs, they'd need converting to PDF (I can do this on request).

## Adding a different photo later
Replace `assets/photo.jpeg` with a same-named file, or update the `src` in the hero section of `index.html` if you rename it.
