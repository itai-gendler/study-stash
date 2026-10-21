---
appliesTo:
- type: entity
  id: recording
- type: entity
  id: phone-recording
- type: entity
  id: lecture
references:
- kind: code
  role: implementation
  target: engine/src/StudyStash.Core/Summarize.cs
- kind: code
  role: implementation
  target: engine/src/StudyStash.Core/Pipeline.cs
---

# Student text remains separate from generated notes

The original personal text travels with the transcript and remains available independently. Generated notes retain student wording and distinguish it from AI writing. Rewriting does not replace the original personal text.
