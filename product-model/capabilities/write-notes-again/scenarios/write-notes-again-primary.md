---
kind: primary
routes:
  desktop: Desktop app
  library-web-library: Library web
steps:
- text: The student asks for a lecture’s notes to be written again, with its attachments or from its library web page.
  kind: actor
  actor: student
  entities:
  - entity: attachment
    effect: reads
    facts: []
  - entity: lecture
    effect: reads
    facts: []
  contexts:
    desktop:
      place: desktop::lecture
    library-web-library:
      place: library-web::library::lecture
- text: The Product queues the lecture again while keeping its filed copy.
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
      place: desktop::lecture
    library-web-library:
      place: library-web::library::lecture
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

# Write notes again

## Trigger

Attachments arrived after a lecture’s notes were written, or the student wants its notes written again.

## Outcome

The lecture is written again from what it has now, and stays readable as it was until the new notes are filed.

## Edge cases

- This processing path writes its result into the lecture; choosing a replacement from another engine uses the separate draft workflow.
- A run producing no new notes preserves existing notes and explains why.
