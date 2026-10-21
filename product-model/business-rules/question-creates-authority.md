---
appliesTo:
- type: entity
  id: question
  effect: creates
permits:
- actors:
  - student
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

# Only the student asks questions

Ask answers questions the student asks.
