---
appliesTo:
- type: entity
  id: edit-draft
references:
- kind: code
  role: implementation
  target: engine/src/StudyStash.App/Services/NoteDrafts.cs
- kind: code
  role: implementation
  target: engine/src/StudyStash.App/Shell.Library.cs
---

# Recent unsaved typing remains recoverable locally

The desktop periodically keeps editor typing and offers it when the lecture is reopened. Local drafts older than thirty days are discarded.
