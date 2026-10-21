---
entities:
- entity: chat
  shows:
  - Title
  - Scope
  - Messages
  - Engine
  - Updated
- entity: class
  shows:
  - Name
- entity: lecture
  shows:
  - Title
references:
- kind: code
  role: implementation
  target: engine/src/StudyStash.Core/Ai/Chats.cs
- kind: code
  role: implementation
  target: engine/src/StudyStash.Library/LibraryWeb.Chat.cs
- kind: code
  role: implementation
  target: ios/StudyStash/Screens/Ask/AskViews.swift
- kind: code
  role: implementation
  target: web/src/screens/Ask.tsx
---

# Ask

Chats in the library’s web pages: saved conversations about the library, a class or a lecture.
