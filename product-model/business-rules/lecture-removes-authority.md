---
appliesTo:
- type: entity
  id: lecture
  effect: removes
references:
- kind: code
  role: implementation
  target: engine/src/StudyStash.Core/Store.cs
- kind: code
  role: implementation
  target: engine/src/StudyStash.Core/LibraryReader.cs
- kind: code
  role: implementation
  target: engine/src/StudyStash.Core/Pipeline.cs
permits:
- actors:
  - student
- unattended: true
---

# Lectures are removed only by the student, or when their deletion can no longer be undone

A deleted lecture stays recoverable for a while and is then removed for good.
