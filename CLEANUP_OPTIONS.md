# Cleanup & organization options

Use this when you want to tidy the repo. Nothing here is required for the site to work.

---

## Done for you

- **`.gitignore`** added so system/editor junk (e.g. `.DS_Store`) isn’t committed.

---

## Docs: what to keep

| File | Purpose |
|------|--------|
| **README.md** | Main project overview and deployment |
| **WORKFLOW_AND_BEST_PRACTICES.md** | How to update the site and avoid path/image issues |
| **MISSING_IMAGES.md** | List of image files still not in the repo (optional reference) |

You can **delete** these if you don’t need the one-time notes anymore:

- `IMAGES_FIX_README.md` (troubleshooting from when images weren’t loading)
- `IMAGES-README.txt` (old image instructions; replaced by WORKFLOW_AND_BEST_PRACTICES.md)

To remove them (optional):

```bash
cd "/Users/alexacarmona/Downloads/cursor tes/portfolio-repo"
git rm IMAGES_FIX_README.md IMAGES-README.txt
git commit -m "Remove one-time image fix docs"
git push origin main
```

---

## Optional: remove duplicate/old folders

Your **live site** is built from the **repo root** (Settings → Pages → Folder: / (root)). So:

- **`portfolio-site/`** – Another copy of the site (index.html + images). Not used for deployment. Safe to delete if you’re sure you only want the root version.
- **`home 6/`** – Looks like an old/backup folder. Safe to delete if you don’t need it.

**Only do this if you’re sure you don’t need these folders.**

To remove them:

```bash
cd "/Users/alexacarmona/Downloads/cursor tes/portfolio-repo"
git rm -r "portfolio-site" "home 6"
git commit -m "Remove duplicate portfolio-site and old home 6 folder"
git push origin main
```

If you prefer to keep them but hide the clutter, you could move them into a single `archive/` folder and commit that instead.

---

## On GitHub.com (repo settings)

- **Description:** In the repo, click the gear next to “About” and set a short description (e.g. “Portfolio – graphic design & photography”).
- **Topics:** Add tags like `portfolio`, `github-pages`, `static-site` so the repo is easier to find.
- **README:** The main README already shows on the repo home; you can add a line at the top like “Live site: https://alexacarmonaportfolio.com” if you want.

---

## Summary

- **Done:** `.gitignore` added.
- **Optional:** Delete `IMAGES_FIX_README.md` and `IMAGES-README.txt`.
- **Optional:** Delete or archive `portfolio-site/` and `home 6/`.
- **On GitHub:** Set description and topics, optionally add live site link in README.
