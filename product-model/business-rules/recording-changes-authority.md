---
appliesTo:
- type: entity
  id: recording
  effect: changes
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
- unattended: true
---

# Recordings change only through the student or the app’s own transcribing and sending

The student records, pauses, names and retries; the app transcribes, sends and follows each recording.
