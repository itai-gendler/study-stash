---
kind: primary
routes:
  library-web-connection: Library web
steps:
- text: The student signs in with the library password on the page an AI app opened, and chooses Allow.
  kind: actor
  actor: student
  entities: []
  contexts: &id001
    library-web-connection:
      place: library-web::connection::ai-consent
- text: The Product accepts the library sign-in and records the named AI app connection.
  kind: product
  entities:
  - entity: ai-connection
    effect: creates
    facts:
    - Name
    - Kind
    - Status
    - Last used
  contexts: *id001
  actor: student
- text: The Product returns the student to the requesting app with the reading connection established.
  kind: product
  entities:
  - entity: student
    effect: changes
    facts:
    - AI connection
  contexts: *id001
  actor: student
references:
- kind: code
  role: implementation
  target: engine/src/StudyStash.Library/ClaudeWeb.cs
- kind: code
  role: implementation
  target: engine/src/StudyStash.Core/ClaudeAccess.cs
---

# Allow AI app

## Trigger

Claude or ChatGPT on the web asks to connect to the student’s library.

## Outcome

The app is connected and reads the library within the choices in AI apps settings.

## Edge cases

- An incorrect library password keeps the request on the sign-in page.
- A cancelled request creates no connection.
