---
kind: edge
routes:
  desktop: Desktop app
steps:
- text: The selected engine fails or returns an empty write-up.
  kind: condition
  entities: []
  contexts:
    desktop:
      place: desktop::lecture
  unattended: true
- text: The Product records the rewrite failure.
  kind: product
  entities:
  - entity: rewrite
    effect: changes
    facts:
    - Problem
    from: Working
    to: Failed
  contexts:
    desktop:
      place: desktop::lecture
references:
- kind: code
  role: implementation
  target: engine/src/StudyStash.Core/Ai/Rewrites.cs
- kind: code
  role: implementation
  target: engine/src/StudyStash.App/ViewModels/AiNotesModel.cs
---

# Keep current notes after rewrite failure

## Trigger

The selected engine fails or returns an empty write-up.

## Outcome

No new notes are offered and the current write-up remains unchanged.
