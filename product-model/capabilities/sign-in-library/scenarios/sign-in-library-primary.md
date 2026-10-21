---
kind: primary
routes:
  library-web-connection: Library web
steps:
- text: The student types the library password on the library’s sign-in page.
  kind: actor
  actor: student
  entities: []
  contexts: &id001
    library-web-connection:
      place: library-web::connection::connection
- text: The Product establishes the student’s library access and returns the browser to the library.
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

# Sign in to library

## Trigger

The student opens the library in a browser that is not signed in.

## Outcome

The browser is signed in and opens the library.

## Edge cases

- An incorrect password keeps the sign-in page open with a problem.
