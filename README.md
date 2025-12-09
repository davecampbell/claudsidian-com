# Claudsidian.com

Your Second Brain, Supercharged - Learn how Claude Code + Obsidian creates the ultimate AI-enhanced productivity system.

## About

Claudsidian is a multi-page Hugo site that teaches the powerful workflow of using Claude Code with Obsidian for knowledge management and productivity.

## Tech Stack

- **Static Site Generator**: [Hugo](https://gohugo.io/)
- **Theme**: [PaperMod](https://github.com/adityatelange/hugo-PaperMod)
- **Hosting**: Netlify (recommended)
- **Version Control**: Git + GitHub

## Local Development

### Prerequisites

- [Hugo Extended](https://gohugo.io/installation/) (v0.112.0 or later)
- Git

### Setup

1. **Clone the repository**:
   ```bash
   git clone https://github.com/YOUR-USERNAME/claudsidian-com.git
   cd claudsidian-com
   ```

2. **Initialize theme submodule**:
   ```bash
   git submodule update --init --recursive
   ```

3. **Run local development server**:
   ```bash
   hugo server -D
   ```

4. **Open in browser**:
   Visit `http://localhost:1313`

### Working with Content

**Create a new blog post**:
```bash
hugo new content posts/my-new-post.md
```

**Create a new page**:
```bash
hugo new content my-page.md
```

**Build the site**:
```bash
hugo
```
The static site will be generated in the `public/` directory.

## Deployment to Netlify

### Option 1: Deploy via Netlify UI (Recommended for first time)

1. **Create GitHub repository**:
   ```bash
   git add .
   git commit -m "Initial commit: Claudsidian site setup"
   git branch -M main
   git remote add origin https://github.com/YOUR-USERNAME/claudsidian-com.git
   git push -u origin main
   ```

2. **Connect to Netlify**:
   - Go to [Netlify](https://app.netlify.com/)
   - Click "Add new site" → "Import an existing project"
   - Choose GitHub and select your `claudsidian-com` repository
   - Configure build settings:
     - **Build command**: `hugo --minify`
     - **Publish directory**: `public`
     - **Environment variables**:
       - `HUGO_VERSION`: `0.152.2` (or your Hugo version)

3. **Configure custom domain**:
   - In Netlify: Site settings → Domain management
   - Add custom domain: `claudsidian.com`
   - Follow DNS configuration instructions
   - SSL will be automatically configured by Netlify

### Option 2: Deploy via Netlify CLI

```bash
# Install Netlify CLI
npm install -g netlify-cli

# Login to Netlify
netlify login

# Initialize site
netlify init

# Deploy
netlify deploy --prod
```

## Site Structure

```
claudsidian-com/
├── content/
│   ├── about.md              # About page
│   ├── getting-started.md    # Getting started guide
│   ├── search.md             # Search page
│   └── posts/                # Blog posts
│       └── *.md
├── themes/
│   └── PaperMod/             # Theme submodule
├── hugo.toml                 # Site configuration
└── README.md
```

## Content Guidelines

### Blog Posts

Place blog posts in `content/posts/`:

```markdown
+++
title = 'Your Post Title'
date = '2025-12-08T12:00:00-05:00'
draft = false
tags = ['tag1', 'tag2']
categories = ['Category']
+++

Your content here...
```

### Pages

Create standalone pages in `content/`:

```markdown
+++
title = 'Page Title'
date = '2025-12-08T12:00:00-05:00'
draft = false
+++

Your content here...
```

## Theme Customization

The PaperMod theme is configured in `hugo.toml`. Key customizations:

- **Profile Mode**: Enabled on homepage with buttons
- **Colors**: Based on Claudsidian brand (purple/pink/orange)
- **Features**: Search, TOC, reading time, code copy buttons
- **Navigation**: Main menu with Home, Getting Started, Blog, About, Search

To modify the theme, edit `hugo.toml` parameters. See [PaperMod documentation](https://github.com/adityatelange/hugo-PaperMod/wiki) for all options.

## Netlify Configuration

Create `netlify.toml` in the root (optional but recommended):

```toml
[build]
publish = "public"
command = "hugo --minify"

[context.production.environment]
HUGO_VERSION = "0.140.1"
HUGO_ENV = "production"
HUGO_ENABLEGITINFO = "true"

[context.deploy-preview]
command = "hugo --buildFuture -b $DEPLOY_PRIME_URL"

[context.branch-deploy]
command = "hugo -b $DEPLOY_PRIME_URL"

[[headers]]
  for = "/*"
  [headers.values]
    X-Frame-Options = "DENY"
    X-XSS-Protection = "1; mode=block"
    X-Content-Type-Options = "nosniff"
    Referrer-Policy = "strict-origin-when-cross-origin"
```

## Forms

Netlify Forms are pre-configured. To add a form:

```html
<form name="contact" method="POST" data-netlify="true">
  <input type="hidden" name="form-name" value="contact">
  <!-- Your form fields -->
</form>
```

## Analytics

To add Google Analytics, update `hugo.toml`:

```toml
[params.analytics.google]
SiteVerificationTag = "YOUR-GA-ID"
```

## SEO

SEO settings are in `hugo.toml` under `[params]`:
- Meta description
- Keywords
- Open Graph tags (automatic via PaperMod)

## Maintenance

### Update Theme

```bash
git submodule update --remote --merge
```

### Update Hugo Version

Current version: `0.152.2`

Update the `HUGO_VERSION` environment variable in Netlify if needed.

## Support

For issues or questions:
- Hugo: https://gohugo.io/documentation/
- PaperMod Theme: https://github.com/adityatelange/hugo-PaperMod/wiki
- Netlify: https://docs.netlify.com/

## License

Content: All rights reserved
Theme (PaperMod): MIT License
