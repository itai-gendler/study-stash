---
appliesTo:
- type: entity
  id: update
- type: entity
  id: recording
references:
- kind: code
  role: implementation
  target: engine/src/StudyStash.App/Services/AppUpdates.cs
---

# Automatic updates wait for recording work to be idle

Active capture, a paused capture and unfinished transcription delay automatic installation.
