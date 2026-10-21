---
appliesTo:
- type: entity
  id: lecture
  effect: changes
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

# Lectures change only through the student or the library’s own processing

The student files, renames, edits and rewrites; the library writes notes, files them and adds rich notes.
