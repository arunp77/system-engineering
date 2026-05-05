# 🚀 Deployment Guide: MkDocs + GitHub Pages

This document explains how to create, run, and deploy a documentation website using MkDocs and GitHub Pages.

---

## 📁 Project Structure

```

system-engineering/
├── docs/
│ ├── index.md
│ ├── chapters/
│ ├── assets/
│ └── stylesheets/
├── mkdocs.yml
├── README.md

```

---

## ⚙️ Step 1: Install Requirements

```bash
pip install mkdocs mkdocs-material
```

Verify installation:

```bash
mkdocs --version
```

---

## 🛠️ Step 2: Configure `mkdocs.yml`

Create or update `mkdocs.yml`:

```yaml
site_name: System Engineering
site_url: https://<your-username>.github.io/system-engineering/

theme:
  name: material

docs_dir: docs

nav:
  - Home: index.md
  - Chapters:
      - Phase 0: chapters/phase-0.md
      - Phase 1: chapters/phase-1.md
  - Appendix:
      - Appendix A: chapters/Appendix-A.md
```

⚠️ Important:

- File paths must match exactly (case-sensitive)
- YAML indentation must be correct

---

## 💻 Step 3: Run Locally

```bash
mkdocs serve
```

Open in browser:

```
http://127.0.0.1:8000
```

---

## 🧪 Step 4: Build Site

```bash
mkdocs build
```

This generates a `site/` folder with HTML files.

---

## 🌐 Step 5: Deploy to GitHub Pages

```bash
mkdocs gh-deploy
```

This will:

- Build the site
- Push to `gh-pages` branch
- Publish automatically

---

## ⚙️ Step 6: Enable GitHub Pages

Go to:

```
GitHub → Repo → Settings → Pages
```

Set:

- Source: `Deploy from branch`
- Branch: `gh-pages`
- Folder: `/ (root)`

---

## 🔄 Updating the Website

Whenever you make changes:

```bash
git add .
git commit -m "update docs"
git push

mkdocs gh-deploy
```

---

## 📌 Adding a New Page

### 1. Create Markdown file

Example:

```
docs/chapters/phase-10.md
```

---

### 2. Add it to navigation

Edit `mkdocs.yml`:

```yaml
- Phase 10: chapters/phase-10.md
```

---

### 3. Preview locally

```bash
mkdocs serve
```

---

### 4. Deploy

```bash
mkdocs gh-deploy
```

---

## 🖼️ Adding Images

Store images in:

```
docs/chapters/images/
```

Use in Markdown:

```markdown
![Example](images/img1.png)
```

---

## 🎨 Custom Styling (Optional)

Create:

```
docs/stylesheets/extra.css
```

Add styles:

```css
.md-header {
  background-color: #1f2937;
}
```

Enable in `mkdocs.yml`:

```yaml
extra_css:
  - stylesheets/extra.css
```

---

## 🔗 Social Links (Optional)

```yaml
extra:
  social:
    - icon: fontawesome/brands/github
      link: https://github.com/<your-username>
    - icon: fontawesome/brands/linkedin
      link: https://linkedin.com/in/<your-id>
```

---

## ⚠️ Common Issues

### ❌ Pages look unstyled

- Likely accessing raw `.md` files
- Always navigate via site URL

---

### ❌ Page not found

- Check file path (case-sensitive)
- Check `nav` in `mkdocs.yml`

---

### ❌ Changes not visible

- Clear cache:
  - `Ctrl + Shift + R`

- Redeploy:

```bash
mkdocs gh-deploy --clean
```

---

## ✅ Final Website URL

```
https://<your-username>.github.io/system-engineering/
```

---

## 🎯 Summary

- Write content in Markdown
- Configure navigation in `mkdocs.yml`
- Test locally using `mkdocs serve`
- Deploy using `mkdocs gh-deploy`

---

## 💡 Future Improvements

- Add diagrams (Mermaid)
- Improve homepage layout
- Add search optimization
- Convert to portfolio-style site

---

````

---

## 👍 Suggestion

Add this file to your repo:

```bash
docs/deployment-guide.md
````

Then include it in navigation:

```yaml
- Deployment Guide: deployment-guide.md
```
