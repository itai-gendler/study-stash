---
singleton: true
references:
- kind: code
  role: implementation
  target: engine/src/StudyStash.Core/GranolaTransfer.cs
- kind: code
  role: implementation
  target: engine/src/StudyStash.App/ViewModels/GranolaSettingsModel.cs
---

# Granola connection

The student’s authorized connection for bringing lectures from Granola.

## Information kept

- **Account** — The account Granola identifies.
- **Connected** — Whether Granola is signed in.
- **Notifications** — Whether newly available lectures are announced.
- **Problem** — Why listing or transfer could not complete.
