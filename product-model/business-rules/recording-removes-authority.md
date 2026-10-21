---
appliesTo:
- type: entity
  id: recording
  effect: removes
references:
- kind: code
  role: implementation
  target: engine/src/StudyStash.Core/Recording/Lectures.cs
- kind: code
  role: implementation
  target: engine/src/StudyStash.Core/Recording/Recorder.cs
permits:
- actors:
  - student
---

# Only the student discards a recording

A recording is discarded only when the student stops a start that captured almost nothing, or leaves an upcoming event’s page without typing anything on it.
