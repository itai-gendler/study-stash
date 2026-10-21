---
kind: primary
routes:
  library-web-library: Library web
steps:
- text: The student chooses Log out.
  kind: actor
  actor: student
  entities: []
  contexts: &id001
    library-web-library:
      place: library-web::library::connection
- text: The Product ends the student’s library access in this browser.
  kind: product
  entities:
  - entity: student
    effect: changes
    facts:
    - Library access
  contexts: *id001
  actor: student
references:
- kind: code
  role: implementation
  target: engine/src/StudyStash.Library/LibraryWeb.cs
---

# Sign out of library

## Trigger

The student is done with the library in this browser.

## Outcome

This browser’s sign-in ends on the library; other browsers stay signed in.
