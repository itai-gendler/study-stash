---
kind: primary
routes:
  library-web-library: Library web
steps:
- text: The student opens a saved chat and asks a follow-up.
  kind: actor
  actor: student
  entities:
  - entity: chat
    effect: reads
    facts: []
  contexts:
    library-web-library: &id001
      place: library-web::library::ask
- text: The Product reads the chat history and adds the next exchange.
  kind: product
  entities:
  - entity: chat
    effect: changes
    facts:
    - Messages
    - Updated
    - Engine
  contexts:
    library-web-library: *id001
  actor: student
references:
- kind: code
  role: implementation
  target: engine/src/StudyStash.Core/Ai/Chats.cs
- kind: code
  role: implementation
  target: engine/src/StudyStash.Library/LibraryWeb.Chat.cs
---

# Continue chat

## Trigger

The student wants to carry on an earlier conversation about their lectures.

## Outcome

The answer follows from the conversation so far and is saved with it.
