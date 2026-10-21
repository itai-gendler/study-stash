---
kind: edge
routes:
  desktop: Desktop app
  library-web-library: Library web
  phone-web-library: Phone web app
  ios-library: iPhone and iPad app
steps:
- text: The notes engine does not answer a writing attempt.
  kind: condition
  unattended: true
  entities: []
  contexts: &id001
    desktop:
      place: desktop::lecture
    library-web-library:
      place: library-web::library::lecture
    phone-web-library:
      place: phone-web::library::lecture
    ios-library:
      place: ios::library::lecture
- text: The Product leaves the lecture queued for another attempt.
  kind: product
  entities:
  - entity: lecture
    effect: changes
    facts:
    - Problem
    from: Writing
    to: Queued
  contexts: *id001
references:
- kind: code
  role: implementation
  target: engine/src/StudyStash.Core/Pipeline.cs
- kind: code
  role: implementation
  target: engine/src/StudyStash.Core/Classify.cs
- kind: code
  role: implementation
  target: engine/src/StudyStash.Core/Store.cs
- kind: code
  role: implementation
  target: engine/src/StudyStash.Core/Summarize.cs
---

# Wait for an unavailable notes engine

## Trigger

The notes engine does not answer a writing attempt.

## Outcome

The lecture returns to the queue; new notes wait for the engine to answer.
