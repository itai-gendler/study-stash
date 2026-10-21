---
kind: alternate
routes:
  library-web-library: Library web
steps:
- text: The student chooses Try again on a lecture whose filing failed.
  kind: actor
  actor: student
  entities:
  - entity: lecture
    effect: reads
    facts:
    - Problem
  contexts:
    library-web-library:
      place: library-web::library::lecture
- text: The Product queues the lecture to be written and filed again.
  kind: product
  actor: student
  entities:
  - entity: lecture
    effect: changes
    from: Failed
    to: Queued
    facts:
    - Problem
  contexts:
    library-web-library:
      place: library-web::library::lecture
references:
- kind: code
  role: implementation
  target: engine/src/StudyStash.Library/LibraryWeb.cs
- kind: code
  role: implementation
  target: engine/src/StudyStash.Core/Store.cs
---

# Try a failed lecture again

## Trigger

A lecture could not be filed and its page says why.

## Outcome

The lecture goes back into the queue and is written and filed again.
