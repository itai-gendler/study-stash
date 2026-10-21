---
references:
- kind: code
  role: implementation
  target: engine/src/StudyStash.Core/Ai/Chats.cs
- kind: code
  role: implementation
  target: engine/src/StudyStash.Library/LibraryWeb.Chat.cs
---

# Chat

A saved conversation scoped to the library, a class or a lecture.

## Information kept

- **Title** — The question naming the conversation.
- **Scope** — The class or lecture being discussed, or the whole library.
- **Messages** — Questions, answers, times and tool activity.
- **Engine** — The provider continuing the conversation.
- **Updated** — When the conversation last changed.
