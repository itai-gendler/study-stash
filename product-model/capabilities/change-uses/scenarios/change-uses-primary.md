---
kind: primary
routes:
  desktop: desktop
  phone-web-library: phone-web-library
  ios-library: ios-library
steps:
- text: The student changes what they use Study Stash for.
  kind: actor
  actor: student
  entities: []
  contexts: &id001
    desktop:
      place: desktop::general
    phone-web-library:
      place: phone-web::library::general
    ios-library:
      place: ios::library::general
- text: The Product saves the library settings uses.
  kind: product
  actor: student
  entities:
  - entity: library-settings
    effect: changes
    facts:
    - Uses
  contexts: *id001
references:
- kind: code
  role: implementation
  target: engine/src/StudyStash.App/ViewModels/LibrarySettingsModel.cs
- kind: code
  role: implementation
  target: web/src/screens/Settings.tsx
- kind: code
  role: implementation
  target: ios/StudyStash/App/AppModel.swift
---

# Change what Study Stash is for

## Trigger

The student changes what they use Study Stash for.

## Outcome

Library group names and lecture or meeting wording follow the selected uses.
