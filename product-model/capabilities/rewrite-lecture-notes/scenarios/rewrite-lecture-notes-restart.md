---
kind: edge
routes:
  desktop: Desktop app
steps:
- text: The library restarts with a rewrite still working.
  kind: condition
  unattended: true
  entities:
  - entity: rewrite
    effect: reads
    facts: []
  contexts: &id001
    desktop:
      place: desktop::lecture
- text: The Product marks the unfinished rewrite failed.
  kind: product
  entities:
  - entity: rewrite
    effect: changes
    facts:
    - Problem
    from: Working
    to: Failed
  contexts: *id001
references:
- kind: code
  role: implementation
  target: engine/src/StudyStash.Core/Ai/Rewrites.cs
- kind: code
  role: implementation
  target: engine/src/StudyStash.App/ViewModels/AiNotesModel.cs
---

# Recover an interrupted rewrite

## Trigger

The library restarts with a rewrite still working.

## Outcome

The attempt reports that it was interrupted; completed proposals survive the restart.
