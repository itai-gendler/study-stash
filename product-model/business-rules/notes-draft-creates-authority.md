---
appliesTo:
- type: entity
  id: notes-draft
  effect: creates
references:
- kind: code
  role: implementation
  target: engine/src/StudyStash.Core/Ai/Rewrites.cs
permits:
- actors:
  - student
---

# Proposed notes come only from a rewrite the student started

A rewrite with the engine the student picked is the only source of proposed notes.
