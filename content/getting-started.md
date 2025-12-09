+++
title = 'Getting Started with Claudsidian'
date = '2025-12-08T21:34:09-05:00'
draft = false
+++

## Your Journey to an AI-Enhanced Second Brain

This guide will walk you through setting up the Claude Code + Obsidian workflow that powers the Claudsidian system.

## What You'll Need

Before you begin, make sure you have:
- [Obsidian](https://obsidian.md/) installed
- [Claude Code CLI](https://docs.anthropic.com/claude/docs/claude-code) installed
- A Claude API account (or Claude Code subscription)
- Basic familiarity with markdown and note-taking

## Step 1: Configure Your Obsidian Vault

First, set up your Obsidian vault for optimal AI integration:

1. **Create a dedicated vault** (or use an existing one)
2. **Organize your folder structure**:
   ```
   MyVault/
   ├── PROJECTS/         # Active projects
   ├── AREAS/            # Areas of responsibility
   ├── RESOURCES/        # Reference materials
   └── ARCHIVES/         # Completed items
   ```
3. **Enable core plugins**: Templates, Daily notes, Backlinks

## Step 2: Install and Configure Claude Code

Install the Claude Code CLI and set it up to work with your vault:

```bash
# Install Claude Code (if you haven't already)
# Follow instructions at: https://docs.anthropic.com/claude/docs/claude-code

# Navigate to your Obsidian vault
cd /path/to/your/ObsidianVault

# Initialize Claude Code
claude init
```

## Step 3: Set Your Working Directory

The key to the Claudsidian workflow is setting Claude Code's working directory to your Obsidian vault:

```bash
# Always work from your vault directory
cd /path/to/your/ObsidianVault

# Or set it in your shell profile
export CLAUDE_WORKSPACE="/path/to/your/ObsidianVault"
```

## Step 4: Create Your First AI-Enhanced Note

Try this workflow:

1. **Start Claude Code** in your vault directory
2. **Ask Claude to help** with a task or project
3. **Have Claude create notes** documenting the conversation
4. **Review and edit** the notes in Obsidian
5. **Link notes together** to build your knowledge graph

Example prompt:
```
I'm working on a new web project. Help me brainstorm the architecture
and create a project note in PROJECTS/ documenting our discussion.
```

## Step 5: Develop Your Workflow

Here are some powerful workflows to explore:

### Project Planning
Ask Claude to help you break down complex projects and create structured notes with tasks, decisions, and timelines.

### Research Synthesis
Have Claude help you synthesize information from multiple sources and create connected notes in your vault.

### Daily Notes Enhancement
Use Claude to help review your daily notes and extract important insights into permanent notes.

### Code Documentation
When working on code projects, have Claude document your decisions and create technical notes in your vault.

## Best Practices

1. **Be explicit about file locations**: Tell Claude exactly where to create or update files
2. **Review everything**: Claude is helpful but you're the curator of your second brain
3. **Link liberally**: Create connections between notes using `[[WikiLinks]]`
4. **Use templates**: Create note templates for common workflows
5. **Keep conversations focused**: One topic per conversation makes better notes

## Next Steps

Now that you have the basics:
- Explore the [Blog](/posts/) for workflow tips and examples
- Experiment with different types of notes and projects
- Build your knowledge graph over time
- Share what you learn with the community

## Need Help?

Having trouble getting started? Check out our blog posts or reach out to the community.

Remember: Your second brain is personal. Adapt this system to match your thinking and working style.
