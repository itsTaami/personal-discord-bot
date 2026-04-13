# Web Search Skill

## Description
Search the web for any topic and return a clear, summarized answer with sources.

## Trigger Conditions
Use this skill when the user asks to:
- Search for something on the web
- Look up information on a topic
- Find recent news about something
- "Search for [topic]"
- "What is [thing]?"
- "Tell me about [topic]"
- "Latest news on [topic]"
- "Look up [something]"

## Instructions
1. Extract the search query from the user's message
2. Use the WebSearch tool with the query
3. Review the top results
4. Summarize the key findings in 3-5 bullet points
5. List the source URLs at the bottom

### Response format:
```
🔍 Results for: "[search query]"

• [Key finding 1]
• [Key finding 2]
• [Key finding 3]

Sources:
- [URL 1]
- [URL 2]
```

## Edge Cases
- If no useful results are found, say so and suggest a refined search term
- Keep summaries concise — no more than 5 bullet points
- If the query is ambiguous, pick the most likely interpretation and mention it
- Do not fabricate information — only report what was found in search results
