---
appliesTo:
- type: entity
  id: lecture
  effect: creates
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

# Lectures come only from the student’s recordings, imports and transfers

A lecture reaches the library when a recording is sent, imported audio is processed or a Granola lecture is transferred, on the student’s behalf.
