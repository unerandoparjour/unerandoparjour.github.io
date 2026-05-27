# A website about my hiking adventures, built with Hugo and the Dream theme

I added several features to the theme:
- Waline comments (powered by Vercel, email optional and less strict spam protection). The original module has a url parsing issue, fixed by myself.
- Multiple languages (French, English and Chinese)
- Pinnable posts
- More understandable icons
- Possibility to load image and mermaid diagrams in the summary
- Two themes: light and dark

For the moment, I'm quite happy with the theme and the features I added. I think I still need a carousel module to display the photos of my hikes.

## Deploy with GitHub Actions

1. Push this **Hugo source** repo to GitHub (not the generated `public/` folder).
2. In the repo: **Settings → Pages → Build and deployment → Source → GitHub Actions**.
3. Every push to `main` runs `.github/workflows/deploy.yml` and publishes the site.

Edit posts on GitHub under `content/posts/...` — the markdown stays in the repo and is downloadable (Raw / clone / zip).

### If CI fails on `themes/dream` submodule

The theme is cloned during CI. Locally, fix a broken submodule once:

```bash
git rm --cached themes/dream
git submodule add https://github.com/g1eny0ung/hugo-theme-dream.git themes/dream
git add .gitmodules
git commit -m "Fix dream theme submodule"
git push
```

Or keep using `process.sh` only for local builds; CI always fetches the theme fresh.

Next steps:
- Add a carousel module to display the photos of my hikes
