---
kind: alternate
routes:
  desktop: Desktop app
  library-web-library: Library web
steps:
- text: The student asks for every lecture’s notes to be written again, and confirms.
  kind: actor
  actor: student
  entities:
  - entity: lecture
    effect: reads
    facts: []
  contexts:
    desktop:
      place: desktop::notes-settings
    library-web-library:
      place: library-web::library::notes-settings
- text: The Product queues the selected lectures again while keeping its filed copy.
  kind: product
  entities:
  - entity: lecture
    effect: changes
    facts:
    - Problem
    from: Filed
    to: Queued
  contexts:
    desktop:
      place: desktop::notes-settings
    library-web-library:
      place: library-web::library::notes-settings
  actor: student
references:
- kind: code
  role: implementation
  target: engine/src/StudyStash.Library/LibraryWeb.App.cs
- kind: code
  role: implementation
  target: engine/src/StudyStash.Library/LibraryWeb.cs
- kind: code
  role: implementation
  target: engine/src/StudyStash.App/ViewModels/AttachmentsModel.cs
- kind: code
  role: implementation
  target: engine/src/StudyStash.Core/Pipeline.cs
---

# Write existing notes again

## Trigger

The student confirms the action to rewrite all existing notes from Notes and sorting or web Settings.

## Outcome

Existing lectures enter the processing queue and retain their filed copies while waiting.
