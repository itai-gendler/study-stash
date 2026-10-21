---
appliesTo:
- type: entity
  id: ai-connection
  effect: creates
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

# Only the student connects an AI app

An AI app is connected by the student, from AI apps settings on this computer or by allowing it on the library’s sign-in page; an app never connects itself.
