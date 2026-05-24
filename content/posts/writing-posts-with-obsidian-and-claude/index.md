+++
title = 'How I Write Claudsidian Posts with Obsidian and Claude'
date = '2026-05-24T00:00:00-05:00'
draft = false
tags = ['workflow', 'obsidian', 'claude-code', 'publishing', 'meta']
description = "The exact workflow I use to write, review, and publish posts on this site — using the same Claude Code + Obsidian system that Claudsidian teaches."
+++

One of my favorite things about the Claudsidian workflow is that it eats its own cooking.
This site — the one teaching you how to use Claude Code with Obsidian — is itself authored using Claude Code with Obsidian.
Here's exactly how it works.

## The Stack

- **Obsidian** — where posts are written and reviewed
- **Claude Code** — generates first drafts, suggests structure, fills gaps
- **Hugo** — static site generator that turns markdown into web pages
- **Netlify** — hosts the site and auto-deploys on every git push
- **Git** — the publish button

The key insight: Obsidian is set up as a vault that *is* the site's content folder. There's no export step, no conversion, no copy-paste. When a post is ready, a single `git push` puts it live.

## The Folder Structure

Each post lives in its own folder — what Hugo calls a "page bundle":

```
content/posts/
├── welcome-to-claudsidian/
│   └── index.md
├── writing-posts-with-obsidian-and-claude/
│   ├── index.md
│   └── workflow-diagram.png    ← images paste directly here
└── your-next-post/
    └── index.md
```

This matters because images paste directly into the post's folder when you're working in Obsidian. No separate image management, no static/ folder, no broken image paths. Hugo picks up everything in the folder as resources for that post.

## Setting Up Obsidian

Open Obsidian and add `~/projects/claudsidian-com/content/posts/` as a vault (or switch your vault to that folder). That's it. Every folder you see in Obsidian is a post. Every `index.md` is the post body.

One setting to configure: Obsidian → Settings → Files & Links → Default location for new attachments → "Same folder as current file." This ensures images paste into the post's bundle folder.

## Writing a Post

### 1. Create the folder

In Obsidian's file explorer, create a new folder with the post's URL slug:

```
writing-posts-with-obsidian-and-claude/
```

Inside it, create `index.md`.

### 2. Add frontmatter

Every post needs this header:

```toml
+++
title = 'Your Post Title'
date = '2026-MM-DDT00:00:00-05:00'
draft = false
tags = ['tag1', 'tag2']
description = "One sentence for card previews and SEO."
+++
```

Set `draft = true` while you're working; flip to `false` when it's ready to publish.

### 3. Write (or have Claude write a first draft)

For posts where Claude does the heavy lifting: open Claude Code with the site repo as the working directory and ask for a draft. Claude can read the existing posts for style reference and write directly into the `index.md` file.

For posts I'm writing myself: I draft in Obsidian, using its preview mode to see how the markdown renders.

### 4. Add images

Paste images directly in Obsidian. They land in the post's folder automatically. Reference them in the body with:

```markdown
![Alt text](filename.png)
```

No path prefix needed — Hugo resolves them from the bundle.

### 5. Review in the browser

Before publishing, preview locally:

```bash
cd ~/projects/claudsidian-com
hugo server
```

Open `http://localhost:1313` and read the post as it will appear. This catches formatting issues that Obsidian's preview misses.

### 6. Publish

```bash
git add content/posts/your-post-slug/
git commit -m "new post: Your Post Title"
git push
```

Netlify picks up the push, runs `hugo --minify`, and the post is live in about 30 seconds. You can watch the build in the Netlify dashboard.

## The Meta Point

Every post on this site is a product of the Claudsidian workflow: Claude Code + Obsidian + a clean content pipeline that gets out of the way. The friction between "idea" and "live post" is one `git push`.

That's what this whole system is about — reducing the activation energy for creating and publishing knowledge. When the tooling disappears, the thinking takes over.

---

*This workflow is detailed in the [Getting Started guide](/getting-started/). The site source is a Hugo project with PaperMod theme, deployed on Netlify.*
