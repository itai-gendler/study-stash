---
kind: edge
routes:
  desktop: Desktop app
  library-web-library: Library web
  phone-web-library: Phone web app
  ios-library: iPhone and iPad app
steps:
- text: The library cannot finish filing a lecture.
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
- text: The Product marks the lecture as failed.
  kind: product
  entities:
  - entity: lecture
    effect: changes
    facts:
    - Problem
    from: Writing
    to: Failed
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

# Retain a failed filing

## Trigger

The library cannot finish filing a lecture.

## Outcome

The item carries a processing failure for another attempt.
