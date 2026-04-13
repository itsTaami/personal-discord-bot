# Reminder Skill

## Description
Set timed reminders that will notify you through the Discord channel.

## Trigger Conditions
Use this skill when the user asks to:
- Set a reminder
- Be reminded of something later
- "Remind me to [task] in [time]"
- "Set a reminder for [time]"
- "Don't let me forget to [task]"
- "In [X] minutes, remind me to [task]"

## Instructions

### Setting a reminder:
1. Extract two things from the message:
   - **What**: the task or message to remind about
   - **When**: how long from now (in minutes or hours)
2. Convert the time to seconds (e.g. "in 30 minutes" = 1800 seconds)
3. Use the ScheduleWakeup tool (or CronCreate if a recurring reminder) to schedule the reminder
4. When the reminder fires, respond with: "⏰ Reminder: [task]"
5. Confirm immediately: "Got it! I'll remind you about '[task]' in [time]."

### Time parsing:
- "in 10 minutes" → 600 seconds
- "in 1 hour" → 3600 seconds
- "in 2 hours 30 minutes" → 9000 seconds

### Reminder response format:
```
⏰ Reminder: [task description]
```

## Edge Cases
- If no time is given, ask: "When would you like to be reminded?"
- If no task is given, ask: "What should I remind you about?"
- Minimum time: 1 minute
- Maximum time: 24 hours — for longer, suggest using a calendar
- Always confirm the reminder with the exact time so the user can verify it's correct
