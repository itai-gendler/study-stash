---
acts: external
kind: system
references:
- kind: code
  role: implementation
  target: engine/src/StudyStash.Core/ClaudeTools.cs
- kind: code
  role: implementation
  target: engine/src/StudyStash.Core/Ai/ToolAccess.cs
---

# AI agent

The student’s own AI app initiating library tool calls on their behalf. The AI engines called by Study Stash itself are outbound services.
