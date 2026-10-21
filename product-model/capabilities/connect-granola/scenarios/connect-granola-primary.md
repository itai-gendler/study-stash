---
kind: primary
routes:
  desktop: Desktop app
steps:
- text: The student chooses Connect and signs in on Granola’s own page.
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

# Connect Granola

## Trigger

The student also records lectures in Granola and wants them in Study Stash.

## Outcome

Granola is connected without Study Stash seeing the password, and its lectures can be offered for transfer.
