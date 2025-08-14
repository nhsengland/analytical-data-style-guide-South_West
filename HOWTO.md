
# 🛠 How to Update and Publish the NHS Analytical Product Design Guide - South West

This guide explains how to correctly update and publish content to the MkDocs-powered site hosted at:

👉 **[https://hannahmitchell35.github.io/analytical-data-style-guide-SW/](https://hannahmitchell35.github.io/analytical-data-style-guide-SW/)**

---

## ⚠️ What *not* to do

- **❌ DO NOT manually change anything in the `gh-pages` branch.**
  > It's automatically managed by GitHub Actions and MkDocs.

- **❌ DO NOT commit directly into `site/` folder (if present locally).**
  > MkDocs builds this from your Markdown and config.

- **❌ DO NOT change GitHub Pages settings in `Settings > Pages` unless absolutely necessary.**

---
# 📁 Repository Process Guide

This guide explains how to make updates to key parts of the *Analytical Data Style Guide SW* repository, including how to modify the site layout, structure, and content.

## 🧩 1. Update the Header or Footer

To customise the **header** or **footer** of the site, edit the relevant HTML partials located in:

```
/analytical-data-style-guide-SW/overrides/partials
```

Look for files such as:
- `header.html` – for modifying the navigation bar or logo
- `footer.html` – for adding or changing footer content like contact info or links

These partials override the default MkDocs theme elements.

---

## 🏠 2. Edit the Homepage Content

To change the content on the **homepage**, edit the Markdown file at:

```
/analytical-data-style-guide-SW/docs/index.md
```

This is the landing page of the site and should give a clear overview of the purpose, scope, and navigation of the guide.

---

## 🔽 3. Add or Modify Dropdown Menu Items

The structure and contents of the **top navigation dropdowns** (and other menu items) are controlled by the MkDocs configuration file:

```
/analytical-data-style-guide-SW/mkdocs.yml
```

To add or change a dropdown section:
- Locate the `nav:` section in the file
- Add or edit entries to include links to the relevant `.md` files in the `docs/` folder
- Follow the existing indentation and structure to preserve formatting

Example:
```yaml
nav:
  - Home: index.md
  - Core Components:
      - Reporting: reporting_corecomponents/index.md
```

---

## 🧱 4. Add a Core Section

To add a **core content section**, create or update a Markdown file in the `docs/` folder:

```
/analytical-data-style-guide-SW/docs
```

Use the following directory as a working example:

```
/analytical-data-style-guide-SW/docs/reporting_corecomponents
```

Each section should contain an `index.md` file and any supporting `.md` pages or subfolders as needed.

---

## 📄 5. Add a Static Content Page (e.g., "About")

For a standalone content page (like **About**, **Contact**, or similar), create a new Markdown file in the `docs/` folder and add a reference to it in `mkdocs.yml`.

Example file:
```
/analytical-data-style-guide-SW/docs/about.md
```

Then update the navigation:
```yaml
nav:
  - About: about.md
```

---

## 🗂️ Summary of Key File Paths

| 🔧 Purpose                     | 📁 File or Folder Path                              |
|-------------------------------|------------------------------------------------------|
| Header/Footer HTML             | `overrides/partials`                                |
| Homepage content               | `docs/index.md`                                     |
| Dropdown menu/navigation       | `mkdocs.yml`                                        |
| Core content sections          | `docs/` (e.g. `docs/reporting_corecomponents/`)     |
| Static content pages           | `docs/` (e.g. `docs/about.md`)                      |

---

 ## 👉 Commit and push changes to the `main` branch**
   ```bash
   git add .
   git commit -m "Add my new page"
   git push origin main
   ```

 ## ⏳ Wait for GitHub Actions to deploy**
   - You'll see a green check mark next to the commit once it's complete.
   - Usually takes 30–60 seconds.

## 🔄 Refresh your published site**
   - Visit: [https://hannahmitchell35.github.io/analytical-data-style-guide-SW/](https://hannahmitchell35.github.io/analytical-data-style-guide-SW/)
   - Do a hard refresh (Ctrl + Shift + R or Cmd + Shift + R) to clear cache.

✅ **Note:** Always commit your changes with clear messages, and review the site locally before pushing to production.


---

## 🛠 What happens behind the scenes?

- Every time you **push to the `main` branch**, GitHub Actions:
  1. Installs the MkDocs dependencies from `requirements.txt`.
  2. Builds your site using `mkdocs build`.
  3. Deploys to the `gh-pages` branch using GitHub Pages native actions.
  4. GitHub Pages serves that `gh-pages` branch as your public site.

You don’t need to manually trigger anything.

---

## 💡 Troubleshooting tips

| Problem | Solution |
|--------|----------|
| Changes not appearing on the website | Wait ~1 min, hard refresh browser |
| Build fails in Actions | Check for YAML errors, missing files in `mkdocs.yml` |
| GitHub Pages showing wrong content | Confirm `gh-pages` is auto-deployed, **do not edit manually** |
| File excluded warning | Ensure file paths in `mkdocs.yml` match actual files |
| You need to "unpublish" a section | Move the folder to `/archived` or comment out from `nav` |


---

## ✅ Final checks before pushing

- [ ] Content added in `docs/`
- [ ] `mkdocs.yml` navigation updated
- [ ] GitHub Actions workflow shows green ✅
- [ ] Site reflects changes after ~1 min







