# 🏕️ Robi Baar Website

Modern, mobile-responsive website for the Abenteuerspielplatz Robi Baar adventure playground in Baar, Switzerland.

Built with [Hugo](https://gohugo.io/) for free hosting on GitHub Pages with Cloudflare DNS.

## 🚀 Quick Start

### Prerequisites

1. Install Hugo (extended version): https://gohugo.io/installation/
2. A GitHub account

### Local Development

```bash
# Clone the repository
git clone https://github.com/YOUR_USERNAME/robi-baar-website.git
cd robi-baar-website

# Start the development server
hugo server -D

# Open http://localhost:1313 in your browser
```

## 📦 Deployment to GitHub Pages

### Step 1: Create GitHub Repository

1. Go to https://github.com/new
2. Create a new repository named `robi-baar-website` (or any name you prefer)
3. Make it public

### Step 2: Push Code to GitHub

```bash
cd robi-baar-hugo
git init
git add .
git commit -m "Initial commit - Robi Baar website"
git branch -M main
git remote add origin https://github.com/YOUR_USERNAME/robi-baar-website.git
git push -u origin main
```

### Step 3: Enable GitHub Pages

1. Go to your repository on GitHub
2. Navigate to **Settings** → **Pages**
3. Under "Build and deployment":
   - Source: Select **GitHub Actions**
4. The workflow will automatically build and deploy your site

### Step 4: Your site is live!

After a few minutes, your site will be available at:
`https://YOUR_USERNAME.github.io/robi-baar-website/`

## 🌐 Custom Domain Setup with Cloudflare

### Step 1: Configure GitHub Pages

1. In your repository, go to **Settings** → **Pages**
2. Under "Custom domain", enter: `robi-baar.ch`
3. Check "Enforce HTTPS"

### Step 2: Create CNAME file

Create a file `static/CNAME` with content:
```
robi-baar.ch
```

### Step 3: Configure Cloudflare DNS

1. Log into Cloudflare dashboard
2. Select your domain (robi-baar.ch)
3. Go to **DNS** settings
4. Add the following records:

**For apex domain (robi-baar.ch):**
| Type | Name | Content |
|------|------|---------|
| A | @ | 185.199.108.153 |
| A | @ | 185.199.109.153 |
| A | @ | 185.199.110.153 |
| A | @ | 185.199.111.153 |

**For www subdomain:**
| Type | Name | Content |
|------|------|---------|
| CNAME | www | YOUR_USERNAME.github.io |

### Step 4: Cloudflare SSL Settings

1. Go to **SSL/TLS** → **Overview**
2. Set encryption mode to **Full** (not Full Strict)

### Step 5: Update hugo.toml

Change the baseURL to your custom domain:
```toml
baseURL = 'https://robi-baar.ch/'
```

## 📁 Project Structure

```
robi-baar-hugo/
├── content/              # Page content (Markdown)
│   ├── _index.md        # Homepage
│   ├── programm.md      # Program page
│   ├── ueber-uns.md     # About page
│   ├── vermietung.md    # Rental page
│   ├── mitgliedschaft.md # Membership page
│   ├── kontakt.md       # Contact page
│   └── datenschutz.md   # Privacy policy
├── themes/
│   └── robi-theme/      # Custom theme
│       ├── layouts/     # HTML templates
│       └── static/      # CSS, JS, images
├── static/              # Static assets
├── hugo.toml            # Hugo configuration
└── .github/workflows/   # GitHub Actions
```

## ✏️ Editing Content

### Modify page content

Edit the Markdown files in the `content/` directory. Hugo uses front matter (YAML between `---`) for metadata.

Example:
```markdown
---
title: "Page Title"
subtitle: "Optional subtitle"
---

Your content here...
```

### Modify styles

Edit `/themes/robi-theme/static/css/style.css`

### Modify navigation

Edit the `[menu]` section in `hugo.toml`

## 🎨 Features

- ✅ Fully responsive (mobile-first design)
- ✅ Fast loading (no JavaScript frameworks)
- ✅ SEO optimized
- ✅ Accessible
- ✅ Modern CSS with CSS Variables
- ✅ Automatic dark mode support (can be added)
- ✅ Free hosting on GitHub Pages
- ✅ Custom domain support via Cloudflare

## 📝 Adding New Pages

1. Create a new `.md` file in `content/`:
```bash
hugo new beispiel.md
```

2. Edit the file with your content

3. Add to navigation in `hugo.toml`:
```toml
[[menu.main]]
  name = "Beispiel"
  url = "/beispiel/"
  weight = 7
```

## 🔧 Configuration

Key settings in `hugo.toml`:

```toml
[params]
  email = "info@robi-baar.ch"
  address = "Im Jöchler 9, 6340 Baar"
  season = "April bis Oktober"
  membershipPrice = "CHF 50.- / Jahr"
```

## 📄 License

This project is open source and available under the MIT License.

---

Made with ❤️ for the children of Baar
