+++
title = 'What People Are Building with Claude + Obsidian — May 2026'
date = '2026-05-24T00:00:00-05:00'
draft = false
tags = ['roundup', 'community', 'obsidian', 'claude-code', 'pkm', 'mcp']
description = "The first in an ongoing series: interesting workflows, tools, and discussions from the Claude + Obsidian community. May 2026 edition."
+++

One of the things I want Claudsidian to do on a regular basis is surface what the community is actually building and saying about this combination of tools. There's a lot of genuine experimentation happening — on Hacker News, in the Obsidian forums, on GitHub — and most of it flies under the radar.

This is the first in an ongoing series. I'll be scanning the web regularly for the most interesting Claude + Obsidian content and collecting it here. Not a firehose — just the things worth your time.

---

## The Karpathy Wiki Pattern, Applied to Obsidian

The most conceptually interesting piece I found this month: Alfonso Fortunato's writeup on [building an Obsidian PKM around Karpathy's LLM Wiki pattern](https://alfonsofortunato.com/blog/obsidian-pkm-llm-wiki/).

The idea, originally from Andrej Karpathy, is that an LLM-maintained wiki beats RAG because it's *compiled* — Claude reads your raw notes and synthesizes them into a structured, interlinked knowledge base, rather than just retrieving chunks at query time. Alfonso applies this to Obsidian: Claude Code handles the file work, linking, and ongoing structure; you focus on reading and making conceptual connections.

The framing that stuck with me: *"The value is not in hoarding notes. It lives in the associations you make between concepts."*

This is exactly the philosophy behind Claudsidian. Worth reading.

---

## A Skill for Zettelkasten-Style Deep Research

A [Show HN post](https://news.ycombinator.com/item?id=47246516) introduced a Claude Code skill that does structured research differently: it runs web searches, breaks findings into atomic notes, links them under Maps of Content, and — crucially — checks your existing vault first to avoid duplicating what you already know.

The result is a knowledge base that *builds on itself* across sessions rather than starting fresh every time. Still experimental, but it's one of the more substantive automation ideas I've seen in this space.

---

## Bringing Claude.ai (Not Just Claude Code) to Obsidian

Most Claude + Obsidian setups assume you're comfortable in a terminal running Claude Code. But a developer on the [Obsidian forum](https://forum.obsidian.md/t/i-built-an-mcp-server-that-connects-claude-ai-directly-to-your-obsidian-vault/112454) built an MCP server that connects Claude.ai — the web interface — directly to a live vault.

Features: full-text fuzzy search across all notes, backlink discovery, daily note creation, append-under-heading. No CLI required. This opens the workflow to people who aren't developers, which matters if the Claude + Obsidian approach is going to spread beyond the technical crowd.

Install: `npm install -g obsidian-claude-mcp`

---

## A Community Starter Kit

If you want to try the Claude + Obsidian workflow without building it from scratch, [obsidian-claude-pkm on GitHub](https://github.com/ballred/obsidian-claude-pkm) is worth a look. It's a complete starter kit: vault structure, CLAUDE.md, an `/onboard` command that personalizes the setup, and a goal-cascade system from three-year vision down to daily tasks.

The onboarding design is smart — instead of reading documentation, you run `/onboard` and answer a few questions. Lower activation energy is a real feature.

---

## The Technical Case for This Combination

If you're trying to explain to someone why Claude Code + Obsidian is a better pairing than, say, Claude + Notion or Claude + Roam, [this Parazettel piece](https://parazettel.com/articles/obsidian-x-claude-code/) makes the argument cleanly: Claude Code operates at the filesystem level, Obsidian uses plain markdown, so the integration is direct with no translation layer. There's no API to authenticate, no export step, no format conversion. Claude reads and writes the same files Obsidian reads and writes.

It's a technical advantage that most comparisons gloss over.

---

## Other Things Worth Noting

- **[Agentic Copilot](https://news.ycombinator.com/item?id=47438423)** — An Obsidian plugin that embeds Claude Code (and other AI CLIs) directly in the Obsidian UI. Early stage, but the idea of collapsing the two-app workflow into one is interesting.

- **[KatmerCode](https://news.ycombinator.com/item?id=47479462)** — A Claude Code + Obsidian setup tuned for academic research: literature review, citation management, structured note extraction. Shows how the core workflow extends into domain-specific use cases.

- **[Ask HN: If you use Obsidian with Claude Code, why?](https://news.ycombinator.com/item?id=46475889)** — A community thread worth reading for real workflows. Two standouts: using Claude to migrate a hand-rolled HTML site into Obsidian Publish, and using it to document large unfamiliar codebases into a searchable internal wiki.

---

That's the May 2026 edition. I'll be back with another roundup next month.

If you spotted something interesting that didn't make the list, or if you've built something worth sharing — [let me know](/about/).

---

*Want these roundups in your inbox? [Subscribe to the Claudsidian newsletter](/signup/).*
