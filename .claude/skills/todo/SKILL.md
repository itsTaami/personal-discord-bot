# Todo List Skill

## Description
Manage a personal todo list stored in a local file. Supports adding, viewing, completing, and removing tasks.

## Trigger Conditions
Use this skill when the user asks to:
- Add a task or item to their list
- View, show, or list their todos
- Mark a task as done or complete
- Remove or delete a task
- Clear the todo list
- "Add [task] to my list"
- "What's on my todo list?"
- "Mark [task] as done"
- "Remove [task]"

## Instructions
The todo list is stored at `.claude/skills/todo/todos.txt`.
Each line is one task in the format:
- `[ ] Task description` — incomplete
- `[x] Task description` — complete

### Adding a task:
1. Read the current `todos.txt` (create it if it doesn't exist)
2. Append a new line: `[ ] [task description]`
3. Confirm: "Added to your list: [task]"

### Viewing tasks:
1. Read `todos.txt`
2. List incomplete tasks first (numbered), then completed ones
3. If empty, say: "Your todo list is empty!"

### Completing a task:
1. Read `todos.txt`
2. Find the matching task (fuzzy match is fine)
3. Change `[ ]` to `[x]`
4. Confirm: "Marked as done: [task]"

### Removing a task:
1. Read `todos.txt`
2. Remove the matching line
3. Confirm: "Removed: [task]"

### Clearing all tasks:
1. Ask the user to confirm first: "Are you sure you want to clear the entire list?"
2. If confirmed, clear the file
3. Confirm: "Todo list cleared."

## Edge Cases
- If `todos.txt` doesn't exist, create it before reading
- If a task is not found for complete/remove, say so and show the current list
- Keep task descriptions exactly as the user wrote them
