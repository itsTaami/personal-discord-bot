# Joke & Quote Skill

## Description
Deliver a random joke or an inspirational/interesting quote on demand. Supports category filtering and repeat requests.

## Trigger Conditions
Use this skill when the user asks for:
- A joke ("tell me a joke", "make me laugh", "say something funny", "got any jokes?")
- A specific type of joke ("tell me a dad joke", "programming joke", "science joke")
- A quote ("give me a quote", "inspire me", "quote of the day", "motivational quote")
- A themed quote ("quote about success", "something about resilience")
- General entertainment or a pick-me-up
- "Another one" or "give me another" after a joke/quote

## Instructions

### For a joke:
1. If a category is specified (dad joke, programming, science, etc.), use WebSearch to find one in that category
2. Otherwise generate a witty original joke or use WebSearch for a fresh one
3. Format with setup and punchline on separate lines
4. Keep it clean and appropriate for all audiences

### For a quote:
1. If the user specifies a theme, search: "inspirational quotes about [theme]"
2. Otherwise search for a general inspirational or thought-provoking quote
3. Vary the source — don't always return the same author
4. Always include the author name

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

**If user asks for "another one":**
- Provide a different joke or quote than the previous response
- Vary the style or category slightly to keep it fresh

## Edge Cases
- If user wants a specific type (programming jokes, dad jokes, science quotes), honor that
- Keep content inoffensive and appropriate
- If asked for another one, provide a different joke/quote — do not repeat
- If WebSearch returns no suitable jokes, generate an original clean joke
