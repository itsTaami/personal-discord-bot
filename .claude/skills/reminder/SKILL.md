# Reminder Skill

## Description
Set timed reminders that will notify you through the Discord channel. Supports one-off reminders with flexible natural language time parsing.

## Trigger Conditions
Use this skill when the user asks to:
- Set a reminder
- Be reminded of something later
- "Remind me to [task] in [time]"
- "Set a reminder for [time]"
- "Don't let me forget to [task]"
- "In [X] minutes, remind me to [task]"
- "Remind me about [task] in [X] hours"
- "Alert me to [task] in [time]"

## Instructions

### Setting a reminder:
1. Extract two things from the message:
   - **What**: the task or message to remind about
   - **When**: how long from now (in minutes or hours)
2. Convert the time to seconds using the parsing rules below
3. Use the ScheduleWakeup tool to schedule the reminder with:
   - `delaySeconds`: the computed number of seconds
   - `reason`: a short label like "reminder: [task]"
   - `prompt`: "Send a Discord reminder message: ⏰ Reminder: [task]"
4. Confirm immediately with the exact time so the user can verify

### Time parsing rules:
| User says | Seconds |
|---|---|
| "in 10 minutes" | 600 |
| "in 1 hour" | 3600 |
| "in 2 hours" | 7200 |
| "in 1 hour 30 minutes" | 5400 |
| "in 90 minutes" | 5400 |
| "in half an hour" | 1800 |

### Confirmation format:
```
Got it! I'll remind you about '[task]' in [X] minutes/hours.
```

### Reminder fire format:
```
⏰ Reminder: [task description]
```

## Edge Cases
- If no time is given, ask: "When would you like to be reminded?"
- If no task is given, ask: "What should I remind you about?"
- Minimum time: 1 minute (60 seconds) — if shorter, say "Minimum reminder time is 1 minute."
- Maximum time: 24 hours — for longer, say "For reminders longer than 24 hours, consider using a calendar app."
- If time is ambiguous (e.g. "in a bit"), ask for clarification
- Always echo back both the task and the time in the confirmation so the user can catch mistakes
