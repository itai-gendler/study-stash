---
kind: primary
routes:
  library-web-library: Library web
steps:
- text: The student deletes a saved chat.
  kind: actor
  actor: student
  entities:
  - entity: chat
    effect: reads
    facts: []
  contexts:
    library-web-library: &id001
      place: library-web::library::ask
- text: The Product removes the chat.
  kind: product
  entities:
  - entity: chat
    effect: removes
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

# Delete chat

## Trigger

A saved conversation is no longer wanted.

## Outcome

The chat is gone from the library; the lectures it discussed are unchanged.
