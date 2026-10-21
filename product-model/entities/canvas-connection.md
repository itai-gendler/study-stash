---
singleton: true
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
---

# Canvas connection

The library’s connection to the student’s Canvas through their signed-in browser.

## Information kept

- **School** — The school’s Canvas address.
- **Browser** — The selected browser and whether its helper is connected.
- **Courses** — Courses discovered and selected for syncing.
- **Last sync** — When the mirror was last refreshed.
- **Problem** — A connection, sign-in or sync problem.
