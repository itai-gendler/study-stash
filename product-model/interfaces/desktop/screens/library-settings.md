---
entities:
- entity: library-settings
  shows:
  - Name
  - Automatic updates
  - Start at login
  collects:
  - Name
  - Connection password
references:
- kind: code
  role: implementation
  target: engine/src/StudyStash.App/ViewModels/LibrarySettingsModel.cs
- kind: code
  role: implementation
  target: engine/src/StudyStash.Core/Config.cs
- kind: code
  role: implementation
  target: engine/src/StudyStash.Library/LibraryWeb.Settings.cs
---

# Library settings

Library settings on the library’s computer: its name and password, whether it starts at login and whether it updates itself.
