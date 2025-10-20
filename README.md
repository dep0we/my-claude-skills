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

Skills will be listed here as they are added.
