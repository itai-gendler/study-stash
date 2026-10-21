---
kind: edge
routes:
  desktop: Desktop app
  library-web-library: Library web
  phone-web-library: Phone web app
  ios-library: iPhone and iPad app
steps:
- text: The notes provider answers with an error rather than being unreachable.
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
- text: The Product files the lecture while retaining its current notes and reporting the failure.
  kind: product
  entities:
  - entity: lecture
    effect: changes
    facts:
    - Problem
    - Filed copy
    from: Writing
    to: Filed
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

# Keep material after a provider error

## Trigger

The notes provider answers with an error rather than being unreachable.

## Outcome

A new lecture is filed with its source material and explanation; an existing write-up is retained.

## Edge cases

- When the engine needs signing in again, the lecture says so, and its notes are written once the engine answers again.
