---
appliesTo:
- type: entity
  id: study-deck
  effect: changes
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

# Only the student practises a study set

Progress is the student’s own answers and cards.
