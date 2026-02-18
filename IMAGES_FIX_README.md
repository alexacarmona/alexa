# Images still not showing – what to check

## 1. GitHub Pages must use repo **root**

- Go to **GitHub** → your repo **alexa** → **Settings** → **Pages**.
- Under **Build and deployment** → **Branch**:
  - Branch: **main**
  - **Folder** must be **"/ (root)"** (not "portfolio-site" or "/docs").
- If it was not root, change it to **"/ (root)"** and **Save**. Wait 2–3 minutes for the site to rebuild.

If the folder was **not** root, the site was being built from a subfolder that doesn’t have the new `images/` folder, so images could not load.

## 2. Test one image directly

In your browser, open:

**https://alexacarmonaportfolio.com/images/alexa_headshot-9.JPG**

- If the image **loads** → paths are correct; try a hard refresh on the main site (⌘+Shift+R).
- If you get **404** → either Pages is still not using root, or the latest commit hasn’t been pushed/deployed.

## 3. Push the latest fix (if you haven’t already)

In Terminal:

```bash
cd "/Users/alexacarmona/Downloads/cursor tes/portfolio-repo"
git add -A
git commit -m "Fix image URLs for custom domain root"
git push origin main
```

Then wait 2–3 minutes and check the site again.

## 4. Hard refresh

- **Mac:** ⌘ + Shift + R  
- **Windows:** Ctrl + Shift + R  

Or open the site in a **private/incognito** window.
