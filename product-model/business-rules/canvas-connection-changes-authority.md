---
appliesTo:
- type: entity
  id: canvas-connection
  effect: changes
references:
- kind: code
  role: implementation
  target: engine/src/StudyStash.Core/Canvas/CanvasSettings.cs
- kind: code
  role: implementation
  target: engine/src/StudyStash.Core/Canvas/CanvasSync.cs
- kind: code
  role: implementation
  target: engine/src/StudyStash.App/ViewModels/CanvasConnectModel.cs
permits:
- actors:
  - student
- unattended: true
---

# The Canvas connection changes only through the student or a Canvas sync

The student sets the school, the browser and the matched courses; a sync records when it ran and any problem.
