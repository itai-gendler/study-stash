---
appliesTo:
- type: entity
  id: notes-draft
  effect: removes
references:
- kind: code
  role: implementation
  target: engine/src/StudyStash.Core/Ai/Rewrites.cs
permits:
- actors:
  - student
---

# Only the student’s choice clears proposed notes

Use new and Keep old each clear the proposal.
