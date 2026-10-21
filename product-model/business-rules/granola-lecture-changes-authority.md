---
appliesTo:
- type: entity
  id: granola-lecture
  effect: changes
references:
- kind: code
  role: implementation
  target: engine/src/StudyStash.Core/GranolaTransfer.cs
permits:
- actors:
  - student
---

# Only the student transfers a Granola lecture or leaves it in Granola

Each offered lecture waits for the student’s Transfer or Leave it.
