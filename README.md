# Portfolio + Pages CMS integration draft

This package connects the current single-file portfolio to editable JSON content while preserving the original HTML/CSS/animation code. The embedded portfolio data remains as a fallback if JSON files cannot be fetched.

## Files
- `index.html`: current portfolio with a loader for CMS-managed JSON.
- `.pages.yml`: Pages CMS configuration.
- `content/`: project tiles, case studies, capabilities, resume, and site settings.
- `media/`: upload CMS images here (create this folder when adding images).

## Important image note
Existing portfolio artwork is still embedded in the original HTML and works with the existing image keys. For a new/changed tile image, upload it through Pages CMS and set the `img` field to the resulting `/media/filename.ext` path. For case-study galleries, set each `gallery` item to a `/media/filename.ext` path. Do not delete the existing image keys unless you replace them with valid media paths.

## Deploy safely
1. Make a backup of the current GitHub `main` branch before replacing anything.
2. Add the files from this package to a separate branch first, including the updated `index.html`, `.pages.yml`, and `content/` JSON files.
3. Ensure the Netlify build publishes the repository root (where `index.html` lives).
4. Preview the branch deploy and check home, Work filters, case studies, About, Resume, mobile layout, scrolling, and animations.
5. Only merge after confirming the preview is correct.
6. In Pages CMS, connect the GitHub repository and authorize the CMS app. It should detect `.pages.yml` and present the editable collections.

If you open the site as a local `file://` URL, browsers block `fetch` for JSON; test using a local web server or a Netlify deploy preview.
