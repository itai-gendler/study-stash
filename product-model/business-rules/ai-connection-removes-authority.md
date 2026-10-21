---
appliesTo:
- type: entity
  id: ai-connection
  effect: removes
references:
- kind: code
  role: implementation
  target: engine/src/StudyStash.App/ViewModels/AiAccessModel.cs
- kind: code
  role: implementation
  target: engine/src/StudyStash.Core/ClaudeAccess.cs
- kind: code
  role: implementation
  target: engine/src/StudyStash.Core/McpClients.cs
permits:
- actors:
  - student
---

# Only the student disconnects an AI app

Disconnecting takes Study Stash out of the app’s own settings, or revokes a connection made from the web.
