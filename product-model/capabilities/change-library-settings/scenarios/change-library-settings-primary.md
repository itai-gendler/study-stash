---
kind: primary
routes:
  desktop: Desktop app
steps:
- text: The student changes the library’s name, whether it starts at login, or whether it updates itself.
  kind: actor
  actor: student
  entities:
  - entity: library-settings
    effect: reads
    facts: []
  contexts:
    desktop:
      place: desktop::library-settings
- text: The Product saves the library settings.
  kind: product
  entities:
  - entity: library-settings
    effect: changes
    facts:
    - Name
    - Automatic updates
    - Start at login
  contexts:
    desktop:
      place: desktop::library-settings
  actor: student
references:
- kind: code
  role: implementation
  target: engine/src/StudyStash.App/ViewModels/LibrarySettingsModel.cs
- kind: code
  role: implementation
  target: engine/src/StudyStash.Library/LibraryWeb.Settings.cs
- kind: code
  role: implementation
  target: engine/src/StudyStash.Core/Config.cs
---

# Change library settings

## Trigger

The student changes the Library section’s settings.

## Outcome

The library uses the chosen name, automatic-update preference and start-at-login preference.
