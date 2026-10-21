---
appliesTo:
- type: entity
  id: chat
  effect: creates
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

# Only the student starts a chat

A chat starts with the student’s first message.
