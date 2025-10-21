# My Claude Skills

Personal collection of Claude Code skills managed with [skillman](https://github.com/chrisvoncsefalvay/skillman).

## Structure

Each skill is contained in its own folder with a `SKILL.md` file that contains the instructions Claude follows when the skill is invoked.

## Installation

To use these skills on another machine:

1. Install skillman:
   ```bash
   uv tool install skillman
   ```

2. Initialize skillman:
   ```bash
   skillman init
   ```

3. Add this repository to your `skills.toml`:
   ```toml
   [skills.my-skills]
   source = "dep0we/my-claude-skills"
   scope = "user"
   ```

4. Sync the skills:
   ```bash
   skillman sync
   ```

## Skills

### agentic-development
Conversational guidance for building software with AI agents, covering workflows, tool selection, prompt strategies, parallel agent management, and best practices based on real-world high-volume agentic development experience.

**Installation:**
```bash
skillman add dep0we/my-claude-skills/agentic-development --scope user --dangerously-skip-permissions
```

### notion-bookmark
Helper skill for creating bookmarks in Notion databases with proper schema validation and metadata extraction.

**Installation:**
```bash
skillman add dep0we/my-claude-skills/notion-bookmark --scope user --dangerously-skip-permissions
```
