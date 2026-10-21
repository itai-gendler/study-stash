---
kind: primary
routes:
  desktop: Desktop app
steps:
- text: The student opens Granola settings.
  kind: actor
  actor: student
  entities: []
  contexts:
    desktop:
      place: desktop::granola
- text: The Product lists each Granola lecture still on offer, newest first, with its date, Transfer and Leave it.
  kind: product
  actor: student
  entities:
  - entity: granola-lecture
    effect: reads
    facts:
    - Title
    - Date
  contexts:
    desktop:
      place: desktop::granola
references:
- kind: code
  role: implementation
  target: engine/src/StudyStash.Core/GranolaTransfer.cs
- kind: code
  role: implementation
  target: engine/src/StudyStash.App/ViewModels/GranolaSettingsModel.cs
---

# Browse Granola lectures

## Trigger

The student wants to see which Granola lectures Study Stash does not have yet.

## Outcome

Every lecture still waiting is listed; ones already transferred or left in Granola are not.

## Edge cases

- The available history and transcript depend on what the connected Granola account supplies.
