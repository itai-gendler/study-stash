---
appliesTo:
- type: entity
  id: voice-memo
  effect: removes
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

# Only the student deletes imported audio

Deleting a failed import removes its uploaded sound.
