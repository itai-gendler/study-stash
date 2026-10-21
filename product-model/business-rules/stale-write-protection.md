---
appliesTo:
- type: entity
  id: lecture
references:
- kind: code
  role: implementation
  target: engine/src/StudyStash.Core/Store.cs
- kind: code
  role: implementation
  target: engine/src/StudyStash.Core/Pipeline.cs
---

# Finishing background work respects newer lecture changes

A removed or changed lecture is not overwritten by an obsolete processing result.
