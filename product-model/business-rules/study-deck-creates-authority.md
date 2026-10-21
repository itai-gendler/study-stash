---
appliesTo:
- type: entity
  id: study-deck
  effect: creates
references:
- kind: code
  role: implementation
  target: web/src/screens/Study.tsx
- kind: code
  role: implementation
  target: ios/StudyStash/Screens/Study/StudyView.swift
permits:
- actors:
  - student
---

# Only the student makes flashcards and a quiz

A study set is made when the student asks for one.
