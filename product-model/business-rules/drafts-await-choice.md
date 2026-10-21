---
appliesTo:
- type: entity
  id: notes-draft
- type: entity
  id: lecture
references:
- kind: code
  role: implementation
  target: engine/src/StudyStash.Core/Ai/Rewrites.cs
- kind: code
  role: implementation
  target: engine/src/StudyStash.App/ViewModels/AiNotesModel.cs
---

# Proposed notes do not replace current notes before acceptance

A completed rewrite keeps its proposal separately. Only Use new changes the lecture’s current notes; Keep old clears the proposal.
