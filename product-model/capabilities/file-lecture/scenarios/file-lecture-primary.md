---
kind: primary
routes:
  desktop: Desktop app
  library-web-library: Library web
  phone-web-library: Phone web app
  ios-library: iPhone and iPad app
steps:
- text: The library finds a queued lecture.
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
- text: The Product claims the queued lecture.
  kind: product
  entities:
  - entity: lecture
    effect: changes
    facts: []
    from: Queued
    to: Writing
  contexts: *id001
- text: The Product writes notes, preserves the supplied personal text and files the lecture.
  kind: product
  entities:
  - entity: lecture
    effect: changes
    facts:
    - Study notes
    - Writer
    - Title
    - Class
    - Topics
    - Filing choice
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

# Write and file lecture

## Trigger

The library finds a queued lecture.

## Outcome

The filed lecture is available to normal library browsing and search.

## Decision points

### Choosing the class

What establishes the destination?

- A student has filed this lecture → keep that class.
- Its recorded class or title matches a class or alias → use the match.
- Otherwise the AI makes a sufficiently confident match → use that class.
- No reliable match is available → keep it in Unsorted.
