# Website Guide - Hexo Blog Reference

## Quick Commands

```bash
# Start local development server (preview at http://localhost:4000)
npm run server

# Build the static site
npm run build

# Clean cache and generated files
npm run clean

# Deploy to GitHub Pages
npm run deploy

# Full rebuild and deploy
npm run clean && npm run build && npm run deploy
```

---

## Creating & Editing Posts

### Create a New Post

```bash
hexo new "My Post Title"
```

This creates: `source/_posts/My-Post-Title.md`

### Create a Draft (not published)

```bash
hexo new draft "Draft Title"
```

This creates: `source/_drafts/Draft-Title.md`

### Publish a Draft

```bash
hexo publish "Draft-Title"
```

### Post Format

Every post starts with YAML front matter:

```yaml
---
title: Post Title
date: 2024-01-15 10:30:00
categories:
  - Music
  - Essays
tags:
  - 港乐
  - reflection
mathjax: true  # optional - enable LaTeX formulas
---

Your content here in Markdown...
```

### Post Location

- Published posts: `source/_posts/`
- Drafts: `source/_drafts/`

---

## Theme Customization

Theme config file: `themes/Chic/_config.yml`

### Change Header Name

```yaml
navname: Felix T.
```

### Change Profile

```yaml
nickname: Felix
description: 瓦器裏有寶貝
avatar: /image/kid.jpeg
```

### Change Navigation Menu

```yaml
nav:
  Posts: /archives
  Categories: /category
  Tags: /tag
  About: /about
```

### Change Social Links

```yaml
links:
  Blog: /archives
  Instagram: https://instagram.com/yourhandle
  Github: https://github.com/yourusername
  Twitter: https://twitter.com/yourhandle
```

### Toggle Features

```yaml
post_toc_enable: true          # Table of contents
post_author_enable: true       # Show author
post_date_enable: true         # Show date
post_category_enable: true     # Show categories
post_copyright_enable: true    # Show copyright notice
```

### Custom CSS

Add custom styles in: `themes/Chic/source/css/custom.styl`

---

## Site Configuration

Main config file: `_config.yml`

### Site Info

```yaml
title: Your Blog Title
subtitle: ''
description: ''
author: Felix Tang
language: en
timezone: ''
```

### URL Settings

```yaml
url: https://felixytang.github.io
root: /
```

### Change Theme

```yaml
theme: Chic
```

---

## Deployment

Currently configured to deploy to GitHub Pages:

- **Repository:** `felixytang/felixytang.github.io`
- **Live URL:** https://felixytang.github.io

### Deployment Settings (in `_config.yml`)

```yaml
deploy:
  type: git
  repo: git@github.com:felixytang/felixytang.github.io.git
  branch: master
```

### Step-by-Step: Update Your Website

1. **Create or edit** a post in `source/_posts/`

2. **Preview locally** (optional but recommended):
   ```bash
   npm run server
   ```
   Open http://localhost:4000 to check your changes

3. **Build and deploy** to live site:
   ```bash
   npm run build && npm run deploy
   ```
   This pushes to GitHub Pages and updates https://felixytang.github.io

4. **Save your source files** to GitHub (keeps your work backed up):
   ```bash
   git add .
   git commit -m "Add new post: Your Post Title"
   git push
   ```

### Quick One-Liner to Update Everything

```bash
npm run clean && npm run build && npm run deploy && git add . && git commit -m "Update blog" && git push
```

---

## Directory Structure

```
new-blog-personal/
├── source/
│   ├── _posts/          # Your blog posts (Markdown files)
│   └── _drafts/         # Draft posts (not published)
├── themes/
│   └── Chic/            # Active theme
│       ├── _config.yml  # Theme settings
│       ├── layout/      # Page templates (EJS)
│       └── source/      # Theme CSS, JS, images
├── scaffolds/           # Templates for new posts
├── public/              # Generated site (don't edit)
├── _config.yml          # Main Hexo config
└── package.json         # Dependencies
```

---

## Useful Features

### Add Images

```markdown
![Alt text](/images/photo.jpg)
```

Place images in `source/images/` folder.

### Code Blocks

````markdown
```javascript
const greeting = "Hello World";
console.log(greeting);
```
````

### LaTeX Formulas

Enable in post front matter with `mathjax: true`, then:

```markdown
Inline: $f(x) = ax + b$

Block:
$$
\sum_{i=1}^{n} x_i
$$
```

### Light/Dark Theme

The site has a built-in toggle button for light/dark mode (top right).

---

## Troubleshooting

### Changes not showing?

```bash
npm run clean && npm run build
```

### Port 4000 in use?

```bash
hexo server -p 4001
```

### Deployment fails?

Check SSH keys are set up for GitHub:
```bash
ssh -T git@github.com
```

---

## Resources

- [Hexo Documentation](https://hexo.io/docs/)
- [Chic Theme](https://github.com/Siricee/hexo-theme-Chic)
- [Markdown Guide](https://www.markdownguide.org/)
