# Image quality on the portfolio

## What’s set up for best quality

- **Full-resolution images in modals:** When you open a project, the site loads the same full-size image files (no separate low-res “thumbnails” in the lightbox).
- **High-quality scaling:** CSS uses `image-rendering: -webkit-optimize-contrast` and `image-rendering: high-quality` so scaled images stay as sharp as the browser allows.
- **Larger display area:** Project detail and scroll areas use `max-width: 1200px` so images can show larger than before (previously 500px / 900px in some places).

## What actually determines quality

1. **Source files**  
   The site always shows the files in your `images/` folder. For the best result:
   - Export at **full resolution** (e.g. 2000px+ on the long side for web).
   - Use **high quality** when exporting (e.g. 90–100% JPEG, or PNG for graphics).
   - Avoid re-saving already compressed images; start from the original edit.

2. **File format**  
   - **Photos:** JPEG at 90–95% quality is a good balance of size and quality.  
   - **Graphics / flat work:** PNG is usually better.

3. **Naming**  
   Keep filenames simple (e.g. `project-01.jpg`) so paths in `index.html` stay correct and you don’t hit “missing image” issues.

If something still looks soft or pixelated, the limit is almost always the **resolution and export quality of the file** in `images/`, not the CSS. Re-export at higher resolution/quality and replace the file (keep the same filename), then refresh the site.
