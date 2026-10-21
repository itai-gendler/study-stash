---
kind: primary
routes:
  desktop: Desktop app
  library-web-library: Library web
  phone-web-library: Phone web app
  ios-library: iPhone and iPad app
steps:
- text: Filed notes are ready and rich notes are requested.
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
- text: The Product reads the filed lecture and adds relevant rich content under surviving headings.
  kind: product
  entities:
  - entity: lecture
    effect: changes
    facts:
    - Study notes
  contexts: *id001
references:
- kind: code
  role: implementation
  target: engine/src/StudyStash.Core/Ai/DiagramJobs.cs
- kind: code
  role: implementation
  target: engine/src/StudyStash.Core/Store.Diagrams.cs
- kind: code
  role: implementation
  target: engine/src/StudyStash.Core/Ai/AiSettings.cs
---

# Add rich notes

## Trigger

Filed notes are ready and rich notes are requested.

## Outcome

Rich content appears within the current notes when it can be designed and inserted.

## Edge cases

- Nothing is added if no illustration would help.
- A failed design leaves the filed words readable.
- An interrupted design is retried up to three attempts.
- New notes take priority over background drawing, and another rewrite replaces the old design work.
