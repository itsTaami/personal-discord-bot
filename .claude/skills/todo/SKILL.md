# Todo List Skill

## Description
Manage a personal todo list stored in a local file. Supports adding, viewing, completing, removing tasks, and assigning priorities.

## Trigger Conditions
Use this skill when the user asks to:
- Add a task or item to their list
- View, show, or list their todos
- Mark a task as done or complete
- Remove or delete a task
- Clear the todo list
- Set or filter by priority
- "Add [task] to my list"
- "What's on my todo list?"
- "Mark [task] as done"
- "Remove [task]"
- "Show my high priority tasks"
- "Add urgent: [task]"

## Instructions
The todo list is stored at `.claude/skills/todo/todos.txt`.
Each line is one task in the format:
- `[ ] Task description` — incomplete, normal priority
- `[!] Task description` — incomplete, high priority
- `[x] Task description` — complete

### Adding a task:
1. Read the current `todos.txt` (create it if it doesn't exist)
2. Check if the user flagged it as urgent/high priority
3. Append a new line: `[ ] [task description]` or `[!] [task description]` for high priority
4. Confirm: "Added to your list: [task]" (mention "high priority" if applicable)

### Viewing tasks:
1. Read `todos.txt`
2. List high priority incomplete tasks first (marked with ⚡), then normal incomplete, then completed
3. Number each incomplete task for easy reference
4. If empty, say: "Your todo list is empty!"

### Completing a task:
1. Read `todos.txt`
2. Find the matching task by number or fuzzy text match
3. Change `[ ]` or `[!]` to `[x]`
4. Confirm: "Marked as done: [task]"

### Removing a task:
1. Read `todos.txt`
2. Remove the matching line
3. Confirm: "Removed: [task]"

### Clearing all tasks:
1. Ask the user to confirm first: "Are you sure you want to clear the entire list?"
2. If confirmed, clear the file
3. Confirm: "Todo list cleared."

### Filtering by priority:
1. Read `todos.txt`
2. Show only lines matching the filter (high priority = `[!]`, incomplete = `[ ]` or `[!]`)

## Edge Cases
- If `todos.txt` doesn't exist, create it before reading
- If a task is not found for complete/remove, say so and show the current list
- Keep task descriptions exactly as the user wrote them
- When user references a task by number, match it to the numbered list shown in the last view
- If the user says "what should I do first?", suggest the top high-priority incomplete task
