# Web Search Skill

## Description
Search the web for any topic and return a clear, summarized answer with sources. Supports news-specific queries and topic-filtered searches.

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
- "Find information about [topic]"
- "What happened with [event]?"

## Instructions
1. Extract the search query from the user's message
2. Determine query type:
   - **News query**: if user asks for "latest", "recent", "news", "today" — append "news" or current year to the search
   - **General query**: search as-is
3. Use the WebSearch tool with the refined query
4. Review the top 3-5 results
5. Synthesize a summary — do not copy-paste, rewrite in plain language
6. List the source URLs at the bottom

### Response format:
```
🔍 Results for: "[search query]"

• [Key finding 1]
• [Key finding 2]
• [Key finding 3]
• [Key finding 4 — if relevant]

Sources:
- [URL 1]
- [URL 2]
```

### For news queries, add a date note:
```
🔍 Latest news: "[topic]"
As of [today's date]:

• [Finding 1]
• [Finding 2]

Sources:
- [URL 1]
```

## Edge Cases
- If no useful results are found, say so and suggest a refined search term
- Keep summaries concise — no more than 5 bullet points
- If the query is ambiguous, pick the most likely interpretation and mention it
- Do not fabricate information — only report what was found in search results
- If results are paywalled or inaccessible, note it and try an alternative query
