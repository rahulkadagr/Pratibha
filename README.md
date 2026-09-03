# Deploying to GitHub Pages

This is a fully static site (HTML + CSS + JS) — no database or backend needed.

## Folder structure
```
portfolio/
├── index.html
├── assets/
│   ├── resume.pdf
│   └── projects/
│       ├── project-financial-statement-analysis.pdf
│       └── project-mutual-fund-dashboard.pdf
```

## Steps
1. Create a new GitHub repository (e.g. `pratibha-portfolio`).
2. Upload this entire folder's contents to the repo root (keep the `assets/` folder structure exactly as-is — the links in `index.html` are relative paths like `assets/resume.pdf`).
3. In the repo: **Settings → Pages → Source** → select the `main` branch and `/ (root)` folder → Save.
4. GitHub gives you a live URL, typically `https://<username>.github.io/<repo-name>/` — it can take a minute to go live.

## Behavior
- **Resume**: the Download Resume buttons use `download="Pratibha_Jain_Resume.pdf"` — clicking them saves the file directly, no new tab.
- **Projects**: each "View Project" button opens the file in a new tab (`target="_blank"`, no `download` attribute) so visitors can read it without a forced save dialog. Two projects are wired up now; the other three show "Project file coming soon" until you add their files.

## Adding the remaining project files
For each remaining project (JK Tyre DCF, NSE automobile analysis, IT companies WACC study):
1. If it's a Word/Excel file, convert it to PDF first — browsers can't preview `.xlsx`/`.docx` natively on a static site.
2. Drop the PDF into `assets/projects/`.
3. In `index.html`, find that project's card and replace:
   `<span class="proj-view disabled">Project file coming soon</span>`
   with:
   `<a class="proj-view" href="assets/projects/your-file.pdf" target="_blank" rel="noopener">View Project ↗</a>`

## Adding a photo
Drop the photo into `assets/` (e.g. `assets/photo.jpg`) and it can be swapped in for the current initials mark in the hero section — send it over and I can wire that up.
