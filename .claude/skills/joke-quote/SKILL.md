# Joke & Quote Skill

## Description
Deliver a random joke or an inspirational/interesting quote on demand.

## Trigger Conditions
Use this skill when the user asks for:
- A joke ("tell me a joke", "make me laugh", "say something funny")
- A quote ("give me a quote", "inspire me", "quote of the day", "motivational quote")
- General entertainment or a pick-me-up

## Instructions

### For a joke:
1. Use WebSearch to find a joke, or generate a witty original one
2. Format with setup on one line and punchline on the next
3. Keep it clean and appropriate for all audiences

### For a quote:
1. If the user specifies a theme (e.g. "quote about success"), search for that specifically
2. Otherwise use WebSearch to find an interesting or inspirational quote
3. Always include the author name

### Response formats:

**Joke:**
```
😄 Here's one for you:

[Setup line]

[Punchline] 🥁
```

**Quote:**
```
💬 "[Quote text]"
— [Author Name]
```

## Edge Cases
- If user wants a specific type (programming jokes, dad jokes, science quotes), honor that
- Keep content inoffensive and appropriate
- If asked for another one, provide a different joke/quote — don't repeat
