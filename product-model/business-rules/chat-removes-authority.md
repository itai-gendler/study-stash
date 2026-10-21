---
appliesTo:
- type: entity
  id: chat
  effect: removes
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

# Only the student deletes a chat

Deleting a chat leaves the lectures it discussed unchanged.
