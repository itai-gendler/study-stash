---
appliesTo:
- type: entity
  id: edit-draft
  effect: changes
references:
- kind: code
  role: implementation
  target: engine/src/StudyStash.App/Services/NoteDrafts.cs
- kind: code
  role: implementation
  target: engine/src/StudyStash.App/ViewModels/AiNotesModel.cs
permits:
- actors:
  - student
---

# Only the student changes an edit draft

An edit draft holds the student’s own unsaved typing.
