---
kind: primary
routes:
  library-web-library: Library web
steps:
- text: The student starts a conversation about the library, a class or a lecture with a first message.
  kind: actor
  actor: student
  entities:
  - entity: class
    effect: reads
    facts: []
  - entity: lecture
    effect: reads
    facts: []
  contexts:
    library-web-library:
      place: library-web::library::ask
- text: The Product creates a chat with the opening message, scope, engine and streamed reply.
  kind: product
  entities:
  - entity: chat
    effect: creates
    facts:
    - Title
    - Scope
    - Messages
    - Engine
    - Updated
  contexts:
    library-web-library:
      place: library-web::library::ask
  actor: student
references:
- kind: code
  role: implementation
  target: engine/src/StudyStash.Core/Ai/Chats.cs
- kind: code
  role: implementation
  target: engine/src/StudyStash.Library/LibraryWeb.Chat.cs
---

# Start chat

## Trigger

The student wants a conversation about their lectures that they can come back to.

## Outcome

A chat named after the question is saved with its answer and can be continued later.

## Edge cases

- An interrupted answer remains associated with its conversation and reports the problem.
