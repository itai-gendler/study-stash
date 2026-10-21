---
appliesTo:
- type: entity
  id: voice-memo
  effect: changes
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
- unattended: true
---

# Imported audio changes only through the student or a computer processing it

A computer that records claims and imports it; the student retries a failed import.
