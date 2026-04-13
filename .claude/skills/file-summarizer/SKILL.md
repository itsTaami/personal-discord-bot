# File Summarizer Skill

## Description
Read and summarize any text file on your machine, giving a concise overview, key points, and action items. Handles large files by summarizing in sections.

## Trigger Conditions
Use this skill when the user asks to:
- Summarize a file or document
- Read and explain the contents of a file
- "Summarize [filename]"
- "What's in [file]?"
- "Give me the key points from [file]"
- "TL;DR of [filename]"
- "Read [filename] for me"
- "Explain what [filename] contains"
- "What does [file] say about [topic]?"

## Instructions
1. Extract the file path or filename from the user's message
2. Use the Read tool to read the file contents
3. Assess the file size:
   - **Short file** (under 100 lines): summarize everything
   - **Medium file** (100–500 lines): focus on the most important sections
   - **Large file** (500+ lines): summarize in logical sections with a section header per part
4. Produce a structured summary:
   - **Overview**: one sentence describing what the file is about
   - **Key Points**: 3–7 bullet points covering the most important content
   - **Action Items** (if any): anything that requires follow-up or decisions

### Response format (short/medium):
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

### Response format (large file):
```
📄 Summary of: [filename] ([N] lines)

Overview: [One sentence description]

Section 1 — [Section name]:
• [Point 1]
• [Point 2]

Section 2 — [Section name]:
• [Point 1]
• [Point 2]

Action Items:
• [Item 1]
```

## Edge Cases
- If the file path is not found, say so clearly and ask the user to provide the correct path
- If the file is very large (>500 lines), summarize in logical sections to keep response readable
- Supported formats: `.txt`, `.md`, `.csv`, `.json`, `.py`, `.js`, `.ts`, `.html`, `.yaml`, `.env` (show keys, not values)
- For `.env` files: list the variable names only, never show values
- For binary files (images, executables, `.docx`, `.pdf`): explain that raw binary cannot be read and suggest converting to text first
- If no filename is given, ask: "Which file would you like me to summarize? Please provide the full path."
- If the user asks about a specific topic within the file ("what does it say about X?"), search for that topic in the summary
