---
entities:
- entity: granola-lecture
  shows:
  - Title
  - Date
  - Material
- entity: granola-connection
  shows:
  - Account
  - Connected
  - Notifications
  - Problem
references:
- kind: code
  role: implementation
  target: engine/src/StudyStash.App/ViewModels/GranolaSettingsModel.cs
- kind: code
  role: implementation
  target: engine/src/StudyStash.Core/GranolaTransfer.cs
---

# Granola

Granola settings: the connected Granola account, whether new lectures are announced, and every lecture waiting to be transferred or left.
