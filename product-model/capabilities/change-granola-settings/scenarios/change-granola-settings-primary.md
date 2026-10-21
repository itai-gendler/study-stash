---
kind: primary
routes:
  desktop: desktop
steps:
- text: The student changes the notification preference.
  kind: actor
  actor: student
  entities: []
  contexts: &id001
    desktop:
      place: desktop::granola
- text: The Product saves the Granola connection notification choice.
  kind: product
  actor: student
  entities:
  - entity: granola-connection
    effect: changes
    facts:
    - Notifications
  contexts: *id001
references:
- kind: code
  role: implementation
  target: engine/src/StudyStash.App/ViewModels/GranolaSettingsModel.cs
- kind: code
  role: implementation
  target: engine/src/StudyStash.Core/GranolaTransfer.cs
---

# Change Granola settings

## Trigger

The student changes the notification preference.

## Outcome

Future checks use the selected notification preference.
