---
appliesTo:
- type: entity
  id: recording-settings
  effect: changes
references:
- kind: code
  role: implementation
  target: engine/src/StudyStash.App/Services/AppHost.cs
- kind: code
  role: implementation
  target: engine/src/StudyStash.App/Services/Settings.cs
permits:
- actors:
  - student
---

# Only the student changes recording settings

Transcription model, language, timing, computer audio, speakers, audio retention and the computer’s role are the student’s choices.
