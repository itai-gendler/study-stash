---
appliesTo:
- type: entity
  id: rewrite
  effect: creates
references:
- kind: code
  role: implementation
  target: engine/src/StudyStash.Core/Ai/Rewrites.cs
permits:
- actors:
  - student
---

# Only the student starts a rewrite

A rewrite starts when the student picks an engine under Rewrite notes with.
