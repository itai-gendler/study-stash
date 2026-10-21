---
kind: primary
routes:
  desktop: Desktop app
steps:
- text: The student chooses Disconnect in Granola settings.
  kind: actor
  actor: student
  entities: []
  contexts: &id001
    desktop:
      place: desktop::granola
- text: The Product changes the Granola connection.
  kind: product
  entities:
  - entity: granola-connection
    effect: changes
    facts:
    - Account
    - Connected
    - Problem
  contexts: *id001
  actor: student
references:
- kind: code
  role: implementation
  target: engine/src/StudyStash.Core/GranolaTransfer.cs
- kind: code
  role: implementation
  target: engine/src/StudyStash.App/ViewModels/GranolaSettingsModel.cs
---

# Disconnect Granola

## Trigger

The student no longer wants Study Stash to look at their Granola.

## Outcome

The Granola sign-in is forgotten on this computer; lectures already brought over stay, and so does the record of what was transferred or left.
