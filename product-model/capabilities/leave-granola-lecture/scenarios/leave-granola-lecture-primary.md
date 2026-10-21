---
kind: primary
routes:
  desktop: Desktop app
steps:
- text: The student chooses Leave it on one of the offered items.
  kind: actor
  actor: student
  entities: []
  contexts:
    desktop:
      place: desktop::granola
- text: The Product marks the Granola lecture left and stops offering it.
  kind: product
  entities:
  - entity: granola-lecture
    effect: changes
    facts: []
    from: Offered
    to: Left
  contexts:
    desktop:
      place: desktop::granola
  actor: student
references:
- kind: code
  role: implementation
  target: engine/src/StudyStash.Core/GranolaTransfer.cs
- kind: code
  role: implementation
  target: engine/src/StudyStash.App/ViewModels/GranolaSettingsModel.cs
---

# Leave lecture in Granola

## Trigger

An offered Granola lecture is not one the student wants in Study Stash.

## Outcome

The lecture stays in Granola and is not offered again, even after reconnecting.
