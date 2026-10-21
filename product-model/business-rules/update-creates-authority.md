---
appliesTo:
- type: entity
  id: update
  effect: creates
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

# Updates are found only by the student’s check or the automatic check

Installed copies look for a new release a few minutes after starting and every six hours, and when the student chooses Check now.
