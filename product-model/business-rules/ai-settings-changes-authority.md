---
appliesTo:
- type: entity
  id: ai-settings
  effect: changes
references:
- kind: code
  role: implementation
  target: engine/src/StudyStash.Core/Ai/AiSettings.cs
- kind: code
  role: implementation
  target: engine/src/StudyStash.Core/Ai/ToolAccess.cs
- kind: code
  role: implementation
  target: engine/src/StudyStash.Core/Ai/Engines.cs
- kind: code
  role: implementation
  target: engine/src/StudyStash.App/ViewModels/AiAccessModel.cs
permits:
- actors:
  - student
---

# Only the student changes Your AI and AI apps settings

Connected AI apps read the library; which engines work for it, and what apps may read, stay the student’s choice.
