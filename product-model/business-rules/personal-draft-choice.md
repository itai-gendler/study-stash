---
appliesTo:
- type: entity
  id: notes-draft
references:
- kind: code
  role: implementation
  target: engine/src/StudyStash.Core/Ai/Rewrites.cs
---

# Only the student decides whether proposed notes replace current notes

Acceptance and dismissal are explicit student choices; completion of the AI attempt is not acceptance.
