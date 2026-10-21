---
appliesTo:
- type: entity
  id: granola-lecture
  effect: creates
references:
- kind: code
  role: implementation
  target: engine/src/StudyStash.Core/GranolaTransfer.cs
permits:
- unattended: true
---

# Granola lectures are offered only by the regular look at Granola

While the app runs it looks at the student’s Granola every few minutes and offers lectures Study Stash does not have.
