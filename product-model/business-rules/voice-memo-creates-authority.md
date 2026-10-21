---
appliesTo:
- type: entity
  id: voice-memo
  effect: creates
references:
- kind: code
  role: implementation
  target: engine/src/StudyStash.Library/VoiceMemos.cs
- kind: code
  role: implementation
  target: engine/src/StudyStash.Core/Recording/VoiceMemoImport.cs
permits:
- actors:
  - student
---

# Only the student imports audio

Imported audio is a sound file the student sent from a phone.
