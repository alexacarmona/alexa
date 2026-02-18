# Fix your push + improve those images

## 1. Fix the rejected push

Your push failed because GitHub has commits you don’t have locally (e.g. from the website or another clone). Sync and push:

```bash
cd "/Users/alexacarmona/Downloads/cursor tes/portfolio-repo"
git pull origin main --rebase
git push origin main
```

If `git pull` asks you to resolve conflicts, fix the files it lists, then:

```bash
git add .
git rebase --continue
git push origin main
```

After this, your latest changes (image quality CSS, untitled-9893 fix, etc.) will be on GitHub and the live site can update.

---

## 2. Why some images still look bad

The site is already set up to show your images at full resolution with high-quality scaling. For **garbage magazine**, **untitled 9893**, **MG 0201**, **MG 2550**, **MG 4375**, and **MG 8277**, the blurriness is coming from the **image files themselves** in `images/`, not from the code.

Those files are either:

- Lower resolution (e.g. small pixel dimensions), or  
- Heavily compressed (e.g. low JPEG quality or over-compressed PNG).

The only way to make them look better is to **replace** those files with better exports.

---

## 3. Replace these files for better quality

Use your **original, high-res edits** and export again. Then **overwrite** the files in `images/` with the **exact same names** so the site keeps working.

| Project / image | Filename in `images/` | What to do |
|-----------------|------------------------|------------|
| Garbage magazine | `_MG_0006.jpg`, `_MG_0077.jpg`, `IMG_5027_3.jpg`, `alexa-atlBikes-8.jpg`, `alexa-atlBikes-19.jpg`, `alexa-atlBikes-24.jpg` | Replace with high-res versions (same names). |
| untitled 9893 | `untitled-9893-17758152-20a1-44f6-9657-a82e442c7166.png` (or keep and also add a clean `untitled-9893.png` if you prefer) | Replace with a full-res export. |
| MG 0201 | `_MG_0201.png` | Replace with higher-res PNG (same name). |
| MG 2550 | `_MG_2550.png` | Replace with higher-res PNG (same name). |
| MG 4375 | `_MG_4375.png` | Replace with higher-res PNG (same name). |
| MG 8277 | `_MG_8277-2.png` | Replace with higher-res PNG (same name). |

**Export settings that usually look good on the web:**

- **Size:** At least **2000px** on the longest side (or full size if the original is smaller).
- **JPEG:** Quality **90–95%**.
- **PNG:** Export without extra compression if your editor has that option.

Then:

1. Overwrite the files in `images/` with these new versions (same filenames).
2. Commit and push:
   ```bash
   git add images/
   git commit -m "Replace low-res images with high-res exports"
   git push origin main
   ```

The site will then serve the new files and they’ll look as good as your new exports.
