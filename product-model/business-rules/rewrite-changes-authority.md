---
appliesTo:
- type: entity
  id: rewrite
  effect: changes
references:
- kind: code
  role: implementation
  target: engine/src/StudyStash.Core/Ai/Rewrites.cs
permits:
- actors:
  - student
- unattended: true
---

# A rewrite ends only by finishing, failing or the student cancelling it

The engine finishes or fails on its own; only the student cancels.
