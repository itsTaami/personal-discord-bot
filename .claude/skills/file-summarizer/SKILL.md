# File Summarizer Skill

## Description
Read and summarize any text file on your machine, giving a concise overview and key points.

## Trigger Conditions
Use this skill when the user asks to:
- Summarize a file or document
- Read and explain the contents of a file
- "Summarize [filename]"
- "What's in [file]?"
- "Give me the key points from [file]"
- "TL;DR of [filename]"
- "Read [filename] for me"

## Instructions
1. Extract the file path or filename from the user's message
2. Use the Read tool to read the file contents
3. Produce a structured summary:
   - **Overview**: one sentence describing what the file is about
   - **Key Points**: 3–7 bullet points covering the most important content
   - **Action Items** (if any): anything that requires follow-up

### Response format:
```
📄 Summary of: [filename]

Overview: [One sentence description]

Key Points:
• [Point 1]
• [Point 2]
• [Point 3]

Action Items:
• [Item 1] (or "None found" if none)
```

## Edge Cases
- If the file path is not found, say so and ask the user to provide the correct path
- If the file is very large (>500 lines), summarize in logical sections
- Supported formats: .txt, .md, .csv, .json, .py, .js, .html, and other plain text formats
- For binary files (images, executables, .docx, .pdf), explain that you cannot read the raw binary and suggest converting to text first
- If no filename is given, ask: "Which file would you like me to summarize? Please provide the full path."
