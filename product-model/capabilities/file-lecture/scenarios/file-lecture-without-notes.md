---
kind: alternate
routes:
  desktop: Desktop app
  library-web-library: Library web
  phone-web-library: Phone web app
  ios-library: iPhone and iPad app
steps:
- text: The library processes a lecture with notes disabled or insufficient source material.
  kind: condition
  unattended: true
  entities:
  - entity: lecture
    effect: reads
    facts: []
  contexts: &id001
    desktop:
      place: desktop::lecture
    library-web-library:
      place: library-web::library::lecture
    phone-web-library:
      place: phone-web::library::lecture
    ios-library:
      place: ios::library::lecture
- text: The Product files the lecture without generating a write-up.
  kind: product
  entities:
  - entity: lecture
    effect: changes
    facts:
    - Class
    - Title
    - Topics
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

# File without generated notes

## Trigger

The library processes a lecture with notes disabled or insufficient source material.

## Outcome

The transcript and original student text remain readable, with the reason no study notes were generated.
