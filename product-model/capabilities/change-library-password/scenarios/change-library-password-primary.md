---
kind: primary
routes:
  desktop: Desktop app
steps:
- text: The student sets a new library password on the library’s computer.
  kind: actor
  actor: student
  entities: []
  contexts: &id001
    desktop:
      place: desktop::library-settings
- text: The Product changes the library settings connection password.
  kind: product
  entities:
  - entity: library-settings
    effect: changes
    facts:
    - Connection password
  contexts: *id001
  actor: student
references:
- kind: code
  role: implementation
  target: engine/src/StudyStash.App/ViewModels/LibrarySettingsModel.cs
- kind: code
  role: implementation
  target: engine/src/StudyStash.Library/LibraryWeb.Settings.cs
---

# Change library password

## Trigger

The student wants a new password for connecting browsers and laptops to the library.

## Outcome

Connecting needs the new password, and browser sign-ins made with the old one end.

## Edge cases

- Browser sessions using the previous password end after replacement.
