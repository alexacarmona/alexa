# Portfolio workflow & best practices

Use this so updates stay simple and you (and any AI/assistant) can work on the project without path or image confusion.

---

## 1. Project structure (keep it simple)

Stick to this layout and don’t mix alternatives:

```
your-repo/
├── index.html          ← main portfolio (single source of truth)
├── about.html
├── design.html
├── photography.html
├── CNAME               ← custom domain (alexacarmonaportfolio.com)
├── images/             ← ALL images go here, nowhere else
│   ├── project1-01.jpg
│   ├── project1-02.jpg
│   └── headshot.jpg
└── README.md
```

**Rules:**
- **One `images/` folder** at the repo root. No images loose in the root, no second `images/` inside another folder.
- **GitHub Pages:** Settings → Pages → Source = **main**, Folder = **/ (root)**. Don’t switch to a subfolder later.
- **Image paths in HTML:** Always `images/filename.jpg` (or `.png`). No paths like `../images/` or `/portfolio-site/images/`.

---

## 2. Image naming (avoids “missing” images)

**Do:**
- Use **short, consistent names**: `projectname-01.jpg`, `projectname-02.png`.
- Match **extension** to the real file: `.jpg` vs `.png` (and stick to one per image).
- Use **lowercase** when you can: `alexa_headshot.jpg` not `Alexa_Headshot.JPG` (avoids case-sensitivity issues).

**Avoid:**
- Letting your system add long suffixes (e.g. `image-5a772518-9d7c-43da.png`). If you have to use such a file, either rename it to something short (e.g. `image.png`) or accept that you’ll have to type that long name in the HTML.
- Putting the same image in two places (root + `images/`) or in a subfolder like `portfolio-site/images/`.

**When adding a new project:**
1. Put image files in `images/` with clear names (e.g. `myproject-01.jpg`, `myproject-02.jpg`).
2. In `index.html`, in the `projects` array, use exactly those names: `"images/myproject-01.jpg"`, etc.
3. Commit and push.

---

## 3. Minor vs major updates

### Minor updates (quick and safe)
- **Change text:** Edit copy in `index.html` (or about/design/photography pages). No path changes.
- **Swap one image:** Replace the file in `images/` with the **same filename** so the HTML doesn’t need to change.
- **Add one project:** Add images to `images/`, add one object to the `projects` array with the correct `images/...` paths.

### Major updates (plan a bit)
- **Redesign / new layout:** Keep `images/` and path convention; change HTML/CSS/structure. Don’t move `images/` or change the Pages “Folder” setting.
- **New section or new page:** Reuse the same rule: all images in `images/`, paths like `images/...`.
- **Moving to a new site generator (e.g. React):** Decide where “images” will live (e.g. `public/images/`) and use one consistent path pattern everywhere.

Before a major change, a quick note like “I’m about to restructure the repo / change the framework” helps an assistant give you a safe plan (e.g. “move files here, then update these paths”).

---

## 4. What to give an AI/assistant so they can help you best

The more of this you share, the fewer back-and-forths and the fewer mistakes (like wrong paths or “missing” images).

### Up front (once per project or when things change)
- **What the project is:** “Portfolio site on GitHub Pages, custom domain alexacarmonaportfolio.com.”
- **Tech:** “Static HTML/CSS/JS, no build step, deployed from repo root.”
- **Important constraints:** “Don’t add npm/Node,” “Keep everything in one folder,” “Images must stay in `images/`.”

### When asking for a feature or fix
- **What you want:** “Add a new photography project,” “Fix images not loading,” “Change the About copy.”
- **Where it lives:** “In `index.html`, the `projects` array around line 760,” or “On the About section.”
- **What you already tried (if any):** “I moved files into `images/` but some still don’t show.”

### When something’s broken
- **What you see:** “Images are missing,” “404 on /images/xyz.jpg.”
- **What you changed last:** “I added 10 new images and a new project,” “I changed the GitHub Pages folder.”
- **Screenshot or exact error:** Especially for 404s or layout issues.

### Nice to have in the repo (so an assistant can self-serve)
- **README.md:** Short description + “Images go in `images/`, paths are `images/filename.ext`.”
- **This file (WORKFLOW_AND_BEST_PRACTICES.md):** So you and the assistant both know the rules.
- **MISSING_IMAGES.md (or similar):** List of images the site expects but that aren’t in the repo yet.

---

## 5. Quick checklist before you push

- [ ] All new/changed images are in **`images/`** (not in root or another folder).
- [ ] In HTML, every image path is **`images/...`** and the **filename + extension** match the file exactly.
- [ ] GitHub Pages is still set to **main** + **/ (root)**.
- [ ] You didn’t rename or remove an image that’s still referenced in the `projects` array.

---

## 6. Summary

- **One place for images:** `images/` at repo root.
- **One place for deployment:** repo root (Pages → / (root)).
- **Consistent names:** short, clear filenames; match extension and path in HTML.
- **When asking for help:** say what you want, where it is, and what you’ve already tried; share constraints and tech.
- **Before big changes:** keep or document the structure (e.g. “images always in `images/`”) so updates stay predictable.

Following this will make future updates (minor or major) easier and help avoid the kind of path and “missing image” issues we fixed this time.
