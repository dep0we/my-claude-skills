# Setup Guide

Complete guide for managing your Claude skills across multiple machines.

## Initial Setup (New Machine)

### 1. Install Prerequisites

```bash
# Install uv (if not already installed)
curl -LsSf https://astral.sh/uv/install.sh | sh

# Install skillman
uv tool install skillman

# Add to PATH (for zsh - adjust for your shell)
echo 'export PATH="$HOME/.local/bin:$PATH"' >> ~/.zshrc
source ~/.zshrc
```

### 2. Authenticate with GitHub

```bash
# Install GitHub CLI
brew install gh

# Login to GitHub
gh auth login

# Configure git to use gh
gh auth setup-git
```

### 3. Install Your Skills

```bash
# Initialize skillman
skillman init

# Add your skills repository
skillman add dep0we/my-claude-skills/notion-bookmark --scope user --dangerously-skip-permissions

# List installed skills
skillman list
```

## Workflow for Managing Skills

### Adding a New Skill

**On your primary machine (where you create skills):**

1. Navigate to your local repo:
   ```bash
   cd ~/my-claude-skills
   ```

2. Create a new skill folder:
   ```bash
   mkdir my-new-skill
   ```

3. Create the SKILL.md file:
   ```bash
   # Edit ~/my-claude-skills/my-new-skill/SKILL.md
   # Add your skill instructions
   ```

4. Commit and push to GitHub:
   ```bash
   git add .
   git commit -m "Add my-new-skill"
   git push origin main
   ```

5. Add the skill to your local installation:
   ```bash
   cd ~
   skillman add dep0we/my-claude-skills/my-new-skill --scope user --dangerously-skip-permissions
   ```

**On other machines:**

```bash
# Just add the new skill
skillman add dep0we/my-claude-skills/my-new-skill --scope user --dangerously-skip-permissions
```

### Updating an Existing Skill

**On your primary machine:**

1. Edit the skill in your local repo:
   ```bash
   cd ~/my-claude-skills/notion-bookmark
   # Edit SKILL.md
   ```

2. Commit and push:
   ```bash
   cd ~/my-claude-skills
   git add .
   git commit -m "Update notion-bookmark skill"
   git push origin main
   ```

3. Update locally:
   ```bash
   cd ~
   skillman update my-claude-skills
   ```

**On other machines:**

```bash
# Update the skill
skillman update my-claude-skills
```

## Quick Reference

### Common Commands

```bash
# List all installed skills
skillman list

# Update a specific skill
skillman update <skill-name>

# Update all skills
skillman update --all

# Remove a skill
skillman remove <skill-name>

# Clean orphaned skills
skillman clean

# Verify a skill structure
skillman verify <skill-name>
```

### Your Repository

- **GitHub**: https://github.com/dep0we/my-claude-skills
- **Local Clone**: ~/my-claude-skills
- **Installed Location**: ~/.claude/skills/user/my-claude-skills

## Troubleshooting

### Skills not showing up in Claude

1. Verify installation:
   ```bash
   ls ~/.claude/skills/user/
   ```

2. Check the SKILL.md exists:
   ```bash
   cat ~/.claude/skills/user/my-claude-skills/SKILL.md
   ```

3. Restart Claude Code

### Git authentication issues

```bash
# Re-authenticate with GitHub
gh auth login
gh auth setup-git
```

### skillman command not found

```bash
# Add to PATH
export PATH="$HOME/.local/bin:$PATH"

# Or permanently add to shell config
echo 'export PATH="$HOME/.local/bin:$PATH"' >> ~/.zshrc
source ~/.zshrc
```
