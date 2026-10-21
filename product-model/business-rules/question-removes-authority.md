---
appliesTo:
- type: entity
  id: question
  effect: removes
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

# Only the student clears questions

Recent questions kept on a phone go only when the student clears them.
