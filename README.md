# StudyToolKit

Free online calculators and productivity tools for students — GPA, attendance, grades, study planning, and everyday time/date and writing calculations. Built with plain HTML, CSS, and vanilla JavaScript. No build step, no backend, no paid services. Designed to be hosted for free on **GitHub Pages**.

## What's included

- A homepage with search, popular tools, categories, and educational guide links.
- 20 working calculators and planning tools (see `tools/`), each with a working interface, input validation, and an explanation of how the calculation works.
- 4 educational guides (see `guides/`) explaining the formulas behind the tools.
- About, Contact, Privacy Policy, Terms of Use, and Disclaimer pages.
- `sitemap.xml`, `robots.txt`, a custom `404.html`, and an SVG favicon.

All calculations run directly in your visitor's browser. The only tool that stores anything is the Study Planner, which uses your browser's own `localStorage` — nothing is sent to a server, because this site has no server-side code at all.

## Before you publish: things to replace

1. **Base URL placeholder.** Every page's `<link rel="canonical">` tag and the `sitemap.xml`/`robots.txt` files use the placeholder:
   `https://YOUR-USERNAME.github.io/studytoolkit/`
   Once your site is live, find-and-replace this placeholder across the project with your actual GitHub Pages URL (see step-by-step below for what that URL will be).

2. **Contact email.** Open `contact/index.html` and replace the placeholder email address with a real one you check.

3. **Legal pages.** `privacy-policy/index.html`, `terms/index.html`, and `disclaimer/index.html` are starter templates, clearly marked as such. Review and adjust them for your actual site before publishing — they are not a substitute for your own legal review.

4. **AdSense (optional, later).** The shared page template includes a clearly commented, empty placeholder for a future approved Google AdSense script. Do not add a publisher ID or ad code until you have an approved AdSense account — see Google's own current policies before applying. Hosting on GitHub Pages does not guarantee AdSense approval.

## How to publish on GitHub Pages (step by step)

1. **Create a free GitHub account** at [github.com](https://github.com) if you don't already have one.
2. **Create a new public repository** named `studytoolkit` (Settings → your profile → "New repository"). Keep it public, and don't initialize it with a README (you already have one here).
3. **Upload the project files.** The easiest way for beginners: on your new repository's page, click "uploading an existing file," then drag in every file and folder from this project (or use `git` — see below).
4. **Open your repository's Settings tab.**
5. **Select "Pages"** in the left sidebar.
6. **Under "Build and deployment," choose "Deploy from a branch."**
7. **Select the `main` branch and the `/ (root)` folder**, then click **Save**.
8. **Wait a minute or two** for GitHub to build and deploy your site. Refresh the Pages settings screen until it shows a published URL.
9. **Open the published URL.** It will look like:
   `https://YOUR-USERNAME.github.io/studytoolkit/`
   (replace `YOUR-USERNAME` with your actual GitHub username).
10. **If something looks broken** (missing styles, broken links, a 404 on the homepage), see Troubleshooting below.

### Publishing with git instead (optional, for more technical users)

```bash
cd studytoolkit
git init
git add .
git commit -m "Initial StudyToolKit site"
git branch -M main
git remote add origin https://github.com/YOUR-USERNAME/studytoolkit.git
git push -u origin main
```
Then follow steps 4–9 above.

## Updating your site after deployment

Edit any file locally (or directly on GitHub.com using the pencil "edit" icon on a file), then either:
- **Via GitHub's web UI:** commit the change directly on github.com — GitHub Pages will redeploy automatically within a minute or two.
- **Via git:** `git add .`, `git commit -m "Update ..."`, `git push`, and GitHub Pages will redeploy automatically.

No build step is required — the files you edit are exactly the files that get served.

## Troubleshooting

- **The homepage loads but has no styling / broken links to tool pages:** Make sure you selected `/ (root)` (not `/docs`) as the Pages source folder in step 7, and that `index.html` is at the very top level of the repository (not inside a subfolder).
- **A tool page shows a 404:** Confirm the repository name is exactly `studytoolkit` and that you're visiting the URL with a trailing slash on folders, e.g. `.../tools/gpa-calculator/`. All internal links in this project use relative paths, so they work correctly whether your repository is named `studytoolkit` or something else — but your base URL (used only in canonical tags and the sitemap) should still be corrected per the step above.
- **CSS or JavaScript doesn't load:** Open your browser's developer console (F12) and check for 404 errors in the Network tab — this usually means a file wasn't uploaded, or was uploaded into the wrong folder. Compare your repository's file structure against the "Project structure" section below.
- **Changes aren't showing up:** GitHub Pages can take a minute or two to redeploy after a push. Try a hard refresh (Ctrl+Shift+R / Cmd+Shift+R) to bypass your browser's cache.

## Project structure

```
studytoolkit/
  index.html
  tools.html
  404.html
  robots.txt
  sitemap.xml
  README.md
  assets/
    css/style.css
    js/main.js
    js/calculators.js
    js/planner.js
    images/favicon.svg
  tools/
    gpa-calculator/index.html
    cgpa-calculator/index.html
    ...18 more tool folders...
  guides/
    how-to-calculate-gpa/index.html
    gpa-vs-cgpa/index.html
    how-to-calculate-attendance/index.html
    how-to-calculate-final-grade/index.html
  about/index.html
  contact/index.html
  privacy-policy/index.html
  terms/index.html
  disclaimer/index.html
```

## Technology

Plain HTML5, CSS3, and vanilla JavaScript only — no frameworks, no build tools, no npm packages, no external fonts or scripts, and no API keys anywhere in the repository. Everything needed to run the site is already in these files.

## License and reuse

You're free to host, modify, and extend this project for your own use. If you make it public, consider keeping it genuinely useful and accurate — the content was written to meet Google's Search Essentials and to avoid overstating what any tool, or free hosting, can guarantee (no promised rankings, traffic, or AdSense approval).
