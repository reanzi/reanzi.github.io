# Raymond Michael Nziku — Resume

Single-page resume, built with React + TypeScript + Vite. Live GitHub
contribution chart pulls from `github-contributions-api.jogruber.de` and
`api.github.com` for `reanzi` — no manual updates needed.

## Deploy to GitHub Pages

This is configured as a **user site**, which publishes at the root of
`https://reanzi.github.io`. That requires the repo to be named exactly
`reanzi.github.io`.

1. Create a new GitHub repository named **`reanzi.github.io`** and push
   this folder to it:

   ```bash
   git init
   git add .
   git commit -m "Initial commit"
   git branch -M main
   git remote add origin https://github.com/reanzi/reanzi.github.io.git
   git push -u origin main
   ```

2. In the repo, go to **Settings → Pages** and set **Source** to
   **GitHub Actions**. The included workflow
   (`.github/workflows/deploy.yml`) builds and deploys automatically on
   every push to `main`.

3. `vite.config.ts` already has `base: "/"`, matching a root-level user
   site. Leave it as is.

4. Push, then check the **Actions** tab — once the workflow finishes,
   your site is live at `https://reanzi.github.io`.

   Note: if you ever rename this repo to something other than
   `reanzi.github.io`, it becomes a project site instead, served at
   `https://reanzi.github.io/<repo-name>/` — in that case, change `base`
   in `vite.config.ts` back to `"/<repo-name>/"`.

## Local development

```bash
npm install
npm run dev
```

## Editing content

All resume content — experience, projects, skills — lives in the arrays
near the top of `src/App.tsx` (`EXPERIENCE`, `PROJECTS`, `SKILLS`). Edit
those directly; no need to touch the layout code below them.
