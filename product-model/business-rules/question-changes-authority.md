---
appliesTo:
- type: entity
  id: question
  effect: changes
permits:
- actors:
  - student
- unattended: true
references:
- kind: code
  role: implementation
  target: engine/src/StudyStash.App/ViewModels/AiAskModel.cs
- kind: code
  role: implementation
  target: web/src/screens/Ask.tsx
- kind: code
  role: implementation
  target: ios/StudyStash/Screens/Ask/AskViews.swift
---

# Questions change only by being answered, stopped or interrupted

An answer streams in for the student; the student can stop it, and an answer cut off by closing the app is marked interrupted.
