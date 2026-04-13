# Project 2: Personal Bot

**Weight:** 20% of final grade
**Duration:** Weeks 11-12
**Emphasis:** Worktrees, sub-agents, skills development, API integration

---

## Overview

Build a functional bot for a messaging platform with at least three distinct capabilities. Choose one of two paths based on your comfort level and interests. Both paths require git worktrees for parallel feature development, sub-agents for research, and GitHub issues for project tracking.

---

## Choose Your Path

| | Path A: Claude Channels (Recommended) | Path B: DIY Bot (Advanced) |
|---|---|---|
| **Approach** | Claude Code skills exposed through a messaging channel | Custom bot built from scratch with Python |
| **Where it runs** | Claude Code on your laptop | Deployed to a cloud server |
| **Intelligence** | Claude handles natural language automatically | You build the logic yourself (optionally with LLM APIs) |
| **Key learning** | Skills authoring, Claude Code customization, channels | API integration, deployment, server management |
| **Difficulty** | Moderate | Harder |

Pick **one path** and follow its requirements below. You cannot mix paths.

---

# Path A: Claude Channels (Recommended)

## Concept

Claude Code has a **channels** feature that connects messaging platforms (Telegram, Discord, Slack, etc.) directly to Claude Code running on your machine. When someone messages the bot, it routes to Claude Code, which uses your custom **skills** to handle the request and responds back through the channel.

Your job is to develop the skills that make the bot useful. The messaging platform is just the interface — the skills are the product.

## How It Works

```
User sends message on Telegram/Discord/Slack
        ↓
Claude Channels routes to Claude Code (local)
        ↓
Claude Code matches to your custom skill
        ↓
Skill executes (reads files, calls APIs, runs scripts)
        ↓
Response sent back through the channel
```

## Platform Options

Choose one messaging platform to connect:

- **Telegram** (recommended) — Easy bot setup via BotFather
- **Discord** — Server-based, good for communities
- **Slack** — Workspace-oriented, good for teams

## Requirements

### 1. Channel Setup

- Set up Claude Channels with your chosen messaging platform
- Bot must be reachable by the instructor and classmates for demo
- Claude Code must be running on your machine during the demo

### 2. At Least 3 Custom Skills

Create at least **3 distinct skills** in your project's `.claude/skills/` directory. Each skill should:

- Have a clear `SKILL.md` with description, trigger conditions, and instructions
- Do something genuinely useful (not just echo text back)
- Handle edge cases gracefully in its instructions

### 3. Skill Ideas

| Category | Skill Examples |
|----------|---------------|
| Information | Look up weather, exchange rates, or news for a given topic |
| Productivity | Manage a todo list stored in a local file, set reminders |
| Research | Search the web and summarize results on a topic |
| File management | Organize, search, or summarize files in a directory |
| Code helper | Generate boilerplate, explain code snippets, review PRs |
| Integration | Read from a local database, query an API, process CSV data |
| Creative | Generate writing prompts, brainstorm ideas, draft emails |

### 4. Git Workflow

- **GitHub issues** — One issue per skill you're building
- **Feature branches** — One branch per skill
- **Git worktrees** — Develop at least two skills in parallel using worktrees
- **Meaningful commits** — Clear history showing iterative development

**Example workflow:**
```bash
# Main development
cd my-bot/

# Create worktree for weather skill
git worktree add ../my-bot-weather feature/weather-skill

# Create worktree for todo skill
git worktree add ../my-bot-todo feature/todo-skill
```

### 5. Documentation

Your README must include:

- Bot description and what it does
- Which platform and how to reach it
- List of all skills with descriptions and example interactions
- Setup instructions (how to get Claude Channels running with your skills)
- Screenshots or examples of conversations

## Deliverables (Path A)

1. **Working bot** — Accessible via messaging platform during demo (Claude Code running)
2. **Custom skills** — At least 3 skills in `.claude/skills/`
3. **Git repository** — With worktree evidence, feature branches, and issues
4. **README** — With skill list, setup instructions, and example interactions
5. **Demo** — Live demo to class in Week 12

## Stretch Goals (Path A)

- More than 3 skills
- Skills that chain together (one skill's output feeds another)
- Skills that use MCP servers for external data
- Skills with supporting scripts (Python, bash) for complex operations
- Multi-turn conversation handling within a skill
- Rich formatting in responses (images, formatted tables)

---

# Path B: DIY Bot (Advanced)

## Concept

Build a bot from scratch using Python and a bot framework library. You write all the code — the bot logic, command handlers, API integrations, and deployment. This is the harder path but gives you full control and deeper understanding of how bots work under the hood.

You may optionally integrate an LLM API (Claude, OpenAI, etc.) to add intelligence, but it's not required — pure Python logic is fine.

## Platform Options

Choose one:

### Option A: Telegram Bot (Recommended)
- python-telegram-bot library
- Easy deployment to free hosting
- Rich message formatting

### Option B: Discord Bot
- discord.py library
- Server management features
- Community-oriented

### Option C: Slack Bot
- Slack Bolt framework
- Workspace integration
- Business-oriented

## Requirements

### 1. At Least 3 Distinct Commands

Each command should do something useful. See the ideas table below for inspiration.

| Category | Examples |
|----------|----------|
| Information | Weather, news headlines, exchange rates |
| Productivity | Reminders, todo lists, timers |
| Fun | Jokes, quotes, random facts |
| Utility | URL shortener, QR generator, translator |
| Integration | Google Calendar, Spotify, GitHub |

### 2. Deployment

Your bot must be **deployed and running on a server** — not just on your laptop.

Free hosting options:
- [Railway.app](https://railway.app/)
- [Fly.io](https://fly.io/)
- [Render.com](https://render.com/)
- Vercel (serverless)
- Replit (always-on)

### 3. Code Organization

- Separate command handlers (not one giant file)
- Config management (no hardcoded tokens!)
- Clean bot initialization
- Error handling — bot responds gracefully to bad input

### 4. Git Workflow

- **GitHub issues** — One issue per command/feature
- **Feature branches** — One branch per command
- **Git worktrees** — Develop at least two commands in parallel using worktrees
- **Meaningful commits** — Clear history showing iterative development

**Example workflow:**
```bash
# Main development
cd bot/

# Create worktree for weather command
git worktree add ../bot-weather feature/weather-command

# Create worktree for reminder command
git worktree add ../bot-reminder feature/reminder-command
```

### 5. Documentation

Your README must include:

- Bot description and purpose
- List of all commands with descriptions
- How to set up (API keys, bot token)
- Deployment instructions
- Example interactions (screenshots welcome)

## Deliverables (Path B)

1. **Working bot** — Deployed and responding to commands
2. **Git repository** — With worktree evidence, feature branches, and issues
3. **README** — With command list, setup instructions, and deployment guide
4. **Demo** — Live demo to class in Week 12

## Stretch Goals (Path B)

- Integration with Claude API or another LLM for AI-powered responses
- MCP server for external data
- User preferences/settings stored persistently
- Multi-step conversations
- Rich formatting (buttons, embeds, inline keyboards)
- Scheduled messages
- Admin commands

---

# Grading (Both Paths)

| Category | Weight | Path A Focus | Path B Focus |
|----------|--------|-------------|-------------|
| Functionality | **35%** | Skills work, bot responds, useful capabilities | Bot works, commands respond, deployed and accessible |
| Process (Git) | 25% | Worktrees, issues, branches, meaningful commits | Worktrees, issues, branches, meaningful commits |
| Code Quality | 20% | Well-structured skills, clear SKILL.md files, clean supporting scripts | Clean handlers, separated concerns, proper error handling |
| Documentation | 10% | README with skill docs, setup guide, examples | README with command docs, setup guide, deployment instructions |
| Creativity | 10% | Interesting/useful skills, good UX | Interesting commands, clever integrations, good UX |

---

# Timeline

### Week 11
- **Choose your path** (A or B)
- Set up your platform (channels or bot framework + token)
- Create GitHub issues for each skill/command
- Implement your first skill/command
- Set up worktrees for parallel development
- Path A: Get channels working with one skill
- Path B: Deploy basic bot to server

### Week 12
- Complete all skills/commands
- Polish and error handling
- Documentation
- **Demo to class**

---

# Tips for Success

### Both Paths
1. **Start simple** — Get one thing working end-to-end before adding more
2. **Use sub-agents** — Have Claude research APIs and documentation for you
3. **Worktrees save time** — Work on multiple features without branch switching
4. **Track with issues** — Each skill/command = one issue = one branch

### Path A Tips
5. **Study existing skills** — Look at how skills are structured in other projects for patterns
6. **Test skills locally first** — Make sure `claude` responds correctly before connecting channels
7. **Write clear SKILL.md files** — The better your instructions, the better Claude handles requests

### Path B Tips
5. **Deploy first** — Get a "hello" bot deployed, then add features
6. **Keep secrets safe** — Use environment variables, never commit tokens
7. **Test in production** — Always verify the deployed bot, not just local

---

# Resources

### Claude Channels (Path A)
- [Claude Code documentation](https://docs.anthropic.com/en/docs/claude-code)
- Look at `.claude/skills/` in this course repo for skill examples

### Telegram
- [python-telegram-bot docs](https://docs.python-telegram-bot.org/)
- [Telegram Bot API](https://core.telegram.org/bots/api)
- [BotFather](https://t.me/botfather) — Create your Telegram bot

### Discord
- [discord.py docs](https://discordpy.readthedocs.io/)
- [Discord Developer Portal](https://discord.com/developers/docs)

### Slack
- [Slack Bolt for Python](https://slack.dev/bolt-python/)
- [Slack API docs](https://api.slack.com/)

### Deployment (Path B)
- [Railway.app](https://railway.app/)
- [Fly.io](https://fly.io/)
- [Render.com](https://render.com/)
