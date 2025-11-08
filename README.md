# Study Site — Auto ZIP Import & Deploy

**Flow**
1. Upload a ZIP to `incoming/` on `main` (any name).  
   The ZIP must be *flat*: `index.html` at the ZIP root (not inside a folder).
2. The **Import website ZIP** workflow extracts the newest (or specified) ZIP and pushes the files to the `site` branch.
3. **Deploy to GitHub Pages** deploys everything on `site`.

**Manual run (if needed)**
- Actions → **Import website ZIP** → Run workflow → set `zip_path` to `incoming/your-file.zip`.

**Maintenance**
- Actions → **Prune old ZIPs** to keep only the newest N ZIPs in `incoming/` (runs weekly by default).

**One-time repo settings**
- Settings → Actions → **Workflow permissions**: *Read and write*.
- Settings → Environments → **github-pages**: allow branch **`site`** (no required reviewers).
- Ensure `.github/workflows/pages-deploy.yml` exists **on the `site` branch** (identical to the one in `main`) so pushes to `site` auto-deploy.
