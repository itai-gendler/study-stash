---
kind: alternate
routes:
  desktop: Desktop app
  library-web-library: Library web
steps:
- text: The engine that writes notes answers again after it needed signing in.
  kind: condition
  unattended: true
  entities: []
  contexts:
    desktop:
      place: desktop::lecture
    library-web-library:
      place: library-web::library::lecture
- text: The Product queues again every lecture filed without notes because that engine needed signing in.
  kind: product
  entities:
  - entity: lecture
    effect: changes
    from: Filed
    to: Queued
    facts:
    - Problem
  contexts:
    desktop:
      place: desktop::lecture
    library-web-library:
      place: library-web::library::lecture
references:
- kind: code
  role: implementation
  target: engine/src/StudyStash.Library/Cli.cs
- kind: code
  role: implementation
  target: engine/src/StudyStash.Core/Ai/Engines.cs
- kind: code
  role: implementation
  target: engine/src/StudyStash.Core/Store.cs
---

# Write the missed notes once the engine is signed in again

## Trigger

The student signs their notes engine in again after it stopped answering for that reason.

## Outcome

The lectures that were filed without notes meanwhile get their notes, without the student asking for each.
