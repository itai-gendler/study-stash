---
appliesTo:
- type: entity
  id: update
  effect: changes
references:
- kind: code
  role: implementation
  target: engine/src/StudyStash.App/Services/AppUpdates.cs
- kind: code
  role: implementation
  target: engine/src/StudyStash.Core/Updates.cs
permits:
- actors:
  - student
- unattended: true
---

# Updates are installed only by the student or by automatic updating

The student chooses Update now; automatic updating waits until nothing is recording or being transcribed.
