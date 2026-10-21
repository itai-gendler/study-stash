---
appliesTo:
- type: entity
  id: lecture
references:
- kind: code
  role: implementation
  target: engine/src/StudyStash.Core/Pipeline.cs
- kind: code
  role: implementation
  target: engine/src/StudyStash.Core/Classify.cs
- kind: code
  role: implementation
  target: engine/src/StudyStash.Core/Store.cs
---

# A student’s filing choice survives later processing

Filing and finishing an AI attempt retain a class explicitly chosen by the student. A title typed by the student likewise survives automatic title generation.
