# CLAUDE.md — Claudsidian Site

Hugo static site at https://claudsidian.com/ — teaching the Claude Code + Obsidian second-brain workflow.

## Stack

- Hugo with PaperMod theme (git submodule at `themes/PaperMod/`)
- Netlify auto-deploy on push to main (`netlify.toml`)
- No backend, no database, no secrets needed

## Content

Posts live in `content/posts/` as **page bundles** — one folder per post, `index.md` inside, images in the same folder.

```
content/posts/
└── post-slug/
    ├── index.md      ← post body + frontmatter
    └── image.png     ← images referenced in body
```

### Post frontmatter

```toml
+++
title = 'Post Title'
date = '2026-MM-DDT00:00:00-05:00'
draft = false
tags = ['tag1', 'tag2']
description = "One sentence for card previews."
+++
```

Keep `draft = true` while writing; flip to `false` to publish.

### Obsidian authoring

Vault is set to `content/posts/`. Images paste directly into the post bundle. Obsidian attachment setting: "Same folder as current file."

## Local Dev

```bash
hugo server        # preview at localhost:1313
hugo server -D     # include drafts
```

## Deploy

```bash
git add content/posts/post-slug/
git commit -m "new post: title"
git push           # Netlify builds and deploys (~30s)
```

## Newsletter Operations

See `~/Documents/dev-brain/projects/claudsidian-com/ops.md` for the Kit newsletter workflow.
Research inbox: `newsletter/research-inbox.md` (gitignored — local only).

## Key Config

- `hugo.toml` — site config, menu, theme params. No secrets.
- `netlify.toml` — build command, security headers, subdomain redirect.
- Analytics tags in `hugo.toml` are placeholders (`XYZabc`) — not yet wired up.
