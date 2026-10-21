---
appliesTo:
- type: entity
  id: chat
  effect: changes
references:
- kind: code
  role: implementation
  target: engine/src/StudyStash.Core/Ai/Chats.cs
- kind: code
  role: implementation
  target: web/src/screens/Ask.tsx
- kind: code
  role: implementation
  target: ios/StudyStash/Screens/Ask/AskViews.swift
permits:
- actors:
  - student
---

# Only the student continues a chat

Each exchange in a chat follows a message from the student.
