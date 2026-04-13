# Project 2 Rubric: Personal Bot

**Weight Distribution:** Balanced with emphasis on functionality

**Two Paths:** Students choose either Path A (Claude Channels) or Path B (DIY Bot). Grade using the criteria for whichever path the student chose. Both paths are graded on the same scale — neither path receives a bonus or penalty.

| Category | Max Score | Weight |
|----------|-----------|--------|
| Functionality | 35 | **35%** |
| Process (Git) | 25 | 25% |
| Code Quality | 20 | 20% |
| Documentation | 10 | 10% |
| Creativity | 10 | 10% |

---

## Functionality (35 points) - **PRIMARY FOCUS**

Does the bot work and respond to user messages?

### Path A: Claude Channels

| Score | Description |
|-------|-------------|
| 32-35 | Bot responds via messaging platform. All 3+ skills work correctly. Claude Code handles requests smoothly. Skills produce useful, well-formatted responses. |
| 27-31 | Bot works well through channels. Skills function as expected. Minor issues with edge cases or response quality. |
| 22-26 | Bot mostly works. Some skills have issues. Channel connection may be intermittent. |
| 16-21 | Basic channel functionality. Some skills broken or poorly instructed. |
| 10-15 | Bot partially works. Limited skill functionality. Channel setup incomplete. |
| 0-9 | Bot doesn't respond or channels not configured. |

**Required (Path A):**
- Claude Channels connected to a messaging platform (Telegram, Discord, or Slack)
- At least 3 custom skills in `.claude/skills/`
- Skills do something genuinely useful
- Bot accessible to instructor during demo (Claude Code running)

### Path B: DIY Bot

| Score | Description |
|-------|-------------|
| 32-35 | Bot works flawlessly. All 3+ commands functional. Deployed and accessible. Handles errors gracefully. Good response times. |
| 27-31 | Bot works well. Commands function as expected. Minor issues with edge cases. |
| 22-26 | Bot mostly works. Some commands have issues. Deployment may be unstable. |
| 16-21 | Basic bot functionality. Some commands broken. Intermittent availability. |
| 10-15 | Bot partially works. Limited functionality. Frequent issues. |
| 0-9 | Bot doesn't run or respond. Not deployed. |

**Required (Path B):**
- At least 3 distinct commands
- Bot deployed and accessible on a server (Telegram, Discord, or Slack)
- Commands actually do something useful
- Appropriate responses to user input

---

## Process (25 points)

Git workflow with worktrees and issues. **Same criteria for both paths.**

| Score | Description |
|-------|-------------|
| 23-25 | Excellent workflow: meaningful commits, feature branches, git worktrees used for parallel development, GitHub issues tracking features. |
| 19-22 | Good commits and branching. Some use of issues or worktrees. |
| 14-18 | Decent commit history. Basic branching. Minimal issue tracking. |
| 9-13 | Few commits. Poor messages. No advanced Git features. |
| 4-8 | Very few commits. No branching or issues. |
| 0-3 | No meaningful Git history. |

**Key elements:**
- Meaningful commit messages
- Feature branches (one per skill/command)
- Git worktrees for parallel development
- GitHub issues for feature tracking
- Sub-agents used for research (bonus)

---

## Code Quality (20 points)

Is the work readable, organized, and maintainable?

### Path A: Claude Channels

| Score | Description |
|-------|-------------|
| 18-20 | Well-structured skills with clear SKILL.md files. Supporting scripts (if any) are clean and organized. Skill instructions are precise and handle edge cases. |
| 14-17 | Good skill structure. SKILL.md files are clear. Minor issues with organization. |
| 10-13 | Skills work but SKILL.md instructions are vague or incomplete. Supporting code could be better organized. |
| 6-9 | Poorly written skill instructions. Disorganized supporting scripts. |
| 3-5 | Hard to understand how skills are meant to work. |
| 0-2 | Skills barely structured. No clear SKILL.md files. |

**Look for (Path A):**
- Clear, well-written SKILL.md files with trigger conditions and instructions
- Supporting scripts are clean and organized (if applicable)
- Skills are self-contained and don't conflict with each other
- Secrets/tokens not hardcoded

### Path B: DIY Bot

| Score | Description |
|-------|-------------|
| 18-20 | Clean, well-organized code. Clear separation of concerns. Consistent style. Error handling present. |
| 14-17 | Mostly clean. Good structure. Minor issues. |
| 10-13 | Readable but could be better organized. Some long functions. |
| 6-9 | Difficult to follow in places. Inconsistent style. |
| 3-5 | Hard to read. Poor organization. |
| 0-2 | Very difficult to understand. |

**Look for (Path B):**
- Clear command handlers
- Separated bot logic from business logic
- Proper error handling
- Config/secrets not hardcoded

---

## Documentation (10 points)

Can someone else set up and use this bot? **Same scoring scale for both paths, different expected content.**

| Score | Description |
|-------|-------------|
| 9-10 | Excellent README: bot description, full skill/command list, setup instructions, example interactions, screenshots. |
| 7-8 | Good README with clear skill/command documentation. |
| 5-6 | Basic documentation. Missing some setup details. |
| 3-4 | Minimal README. Hard to set up without help. |
| 1-2 | Very sparse documentation. |
| 0 | No documentation. |

**README should include (Path A):**
- Bot description and what it does
- Which messaging platform and how to reach it
- List of all skills with descriptions and example interactions
- How to set up Claude Channels with these skills
- Screenshots of conversations

**README should include (Path B):**
- Bot description and purpose
- List of all commands with descriptions
- How to set up (API keys, bot token)
- Deployment instructions
- Example interactions (screenshots welcome)

---

## Creativity (10 points)

Did the student create something interesting?

| Score | Description |
|-------|-------------|
| 9-10 | Impressive bot with unique capabilities. Great UX. Potentially useful in daily life. Shows initiative beyond requirements. |
| 7-8 | Notable features beyond basic skills/commands. Good user experience. |
| 5-6 | Some extras or personalization. Functional but not exceptional. |
| 3-4 | Met minimum requirements. Basic skills/commands only. |
| 1-2 | Bare minimum. Generic implementation. |
| 0 | Below requirements. |

**Examples of creativity (Path A):**
- Skills that chain together or build on each other
- Skills with supporting scripts for complex operations
- MCP server integration for external data
- Multi-turn conversation handling
- Rich response formatting

**Examples of creativity (Path B):**
- Clever/useful commands
- Integration with external APIs
- Persistent data/user preferences
- Rich message formatting (embeds, buttons)
- Scheduled messages or reminders
- Multi-step conversations
