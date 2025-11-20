# Personal Blog — GitHub Pages + Jekyll  
This repository contains the source code of my personal technical blog, built with **Jekyll** and deployed through **GitHub Pages**.  
The blog covers topics such as **AI systems, RAG architecture, OCT imaging, research workflows, and personal reflections**.

---

## 📌 Live Site  
https://www.wjkim.com

---

## 📂 Repository Structure

```

_data/               # Site data files (categories, tags, archives)
_drafts/             # Unpublished posts (Jekyll drafts)
_layouts/            # HTML layouts for posts/pages
_posts/              # Published posts (structured by year/month)
assets/images/       # Blog images and static assets

.gitignore           # Files ignored by Git
CNAME                # Custom domain configuration
_config.yml          # Jekyll and site configuration
about.md             # About page
categories.md        # Categories page
index.md             # Home page
tags.md              # Tags page

````

---

## 🛠 Local Development

### 1. Install Ruby and Bundler  
Make sure Ruby is installed (recommended: `rbenv` for macOS or RubyInstaller for Windows).

```bash
gem install bundler
bundle install
````

### 2. Run the blog locally

```bash
bundle exec jekyll serve
```

Local preview:

```
http://localhost:4000
```

If you want to show **future-dated posts** while testing locally:

```bash
bundle exec jekyll serve --future
```

---

## 🚀 Deployment (GitHub Pages)

The site is automatically built and deployed when pushing to the **main** branch.

### Notes

* GitHub Pages uses **UTC timezone**, so posts with future dates may remain hidden until the date passes (unless rebuilt afterward).
* To force a rebuild after the date passes, you can push a trivial commit:

  ```bash
  git commit --allow-empty -m "trigger rebuild"
  git push
  ```

---

## 📚 Features

* **Minima theme** with custom layouts
* **Tag archive pages (jekyll-archives)**
* **Custom domain (CNAME)**
* **Drafts workflow** (`_drafts/` folder)
* **Structured images folder**
* **Bilingual posts (Korean + English)**
* **Optimized for technical writing and AI system documentation**

---

## ✏️ Writing Workflow

1. Write drafts in `_drafts/`
2. Move to `_posts/YYYY-MM-DD-title.md` when ready
3. Use local preview for formatting checks
4. Push to `main` → GitHub Pages auto-deploy

---

## 📄 License

This blog content is personal and not intended for redistribution.
Code snippets may be used freely with attribution.