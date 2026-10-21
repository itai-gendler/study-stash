---
appliesTo:
- type: entity
  id: notes-draft
  effect: changes
references:
- kind: code
  role: implementation
  target: engine/src/StudyStash.Core/Ai/Rewrites.cs
permits:
- actors:
  - student
---

# Only the student chooses Use new or Keep old

The proposal is accepted or dismissed by the student’s choice alone.
