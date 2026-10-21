---
type: agent
actors:
- ai-agent
references:
- kind: code
  role: implementation
  target: engine/src/StudyStash.Core/ClaudeTools.cs
- kind: code
  role: implementation
  target: engine/src/StudyStash.Core/Ai/ToolAccess.cs
- kind: code
  role: implementation
  target: engine/src/StudyStash.Library/ClaudeWeb.cs
---

# AI apps

The student’s connected AI app browses and reads library material through the supported MCP tools. Local and remote connections use the same reading contract, with the available file tools described in their scenarios.
