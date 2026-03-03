[README.md](https://github.com/user-attachments/files/25720943/README.md)
# Locked In — Interaction Plots

Interactive visualization of expected AI Threat × NFCC interaction patterns for the *Locked In* RCSA grant proposal.

## What's in this repo

| File | Purpose |
|------|---------|
| `index.html` | Self-contained site — all React/JSX compiled in-browser via Babel CDN. No build step needed. |

## Deploy to GitHub Pages (5 steps)

1. **Create a new GitHub repository** (e.g. `locked-in-plots`).

2. **Push this folder:**
   ```bash
   git init
   git add index.html README.md
   git commit -m "initial commit"
   git branch -M main
   git remote add origin https://github.com/YOUR_USERNAME/locked-in-plots.git
   git push -u origin main
   ```

3. **Enable GitHub Pages:**  
   Go to **Settings → Pages → Source** and select `main` branch, root `/` folder. Click **Save**.

4. **Your site will be live at:**  
   `https://YOUR_USERNAME.github.io/locked-in-plots/`
   (GitHub typically deploys within 1–2 minutes.)

5. **To update:** edit `index.html`, commit, and push. Pages re-deploys automatically.

---

## Local preview (optional)

Open `index.html` directly in a browser — it works without a server because everything loads from CDN.

Or run a tiny local server:
```bash
python3 -m http.server 8080
# then visit http://localhost:8080
```

---

## Tech notes

- **React 18** + **Babel standalone** loaded from `unpkg.com` — no npm, no build tooling.
- Y-axis ticks are computed with a `niceTicks()` function that constrains steps to 1/2/5/10 × 10^n, ensuring clean round intervals regardless of data range.
- All plot data (value pairs, axis ranges, annotation copy) lives in the `PLOTS` array at the top of the script — easy to update when hypothetical values change.
