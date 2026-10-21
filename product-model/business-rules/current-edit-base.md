---
appliesTo:
- type: entity
  id: lecture
- type: entity
  id: edit-draft
references:
- kind: code
  role: implementation
  target: engine/src/StudyStash.Core/Store.Edits.cs
- kind: code
  role: implementation
  target: engine/src/StudyStash.App/ViewModels/AiNotesModel.cs
---

# Saving edited notes requires the current base text

A stale editor keeps the student’s typing and reports changed notes. Refreshing the base lets a subsequent explicit save replace the current text.
