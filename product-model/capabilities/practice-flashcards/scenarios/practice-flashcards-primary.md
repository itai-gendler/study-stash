---
kind: primary
routes:
  phone-web-library: Phone web app
  ios-library: iPhone and iPad app
steps:
- text: The student turns over each flashcard and says whether it needs another pass.
  kind: actor
  actor: student
  entities: []
  contexts: &id001
    phone-web-library:
      place: phone-web::library::study
    ios-library:
      place: ios::library::study
- text: The Product presents the study deck cards and records this practice session’s progress.
  kind: product
  entities:
  - entity: study-deck
    effect: changes
    facts:
    - Progress
  contexts: *id001
  actor: student
references:
- kind: code
  role: implementation
  target: web/src/screens/Study.tsx
- kind: code
  role: implementation
  target: ios/StudyStash/Screens/Study/StudyView.swift
---

# Practice flashcards

## Trigger

The student is practising a lecture’s flashcards.

## Outcome

Known cards leave the pass, and cards marked Again come back until the pass is done.

## Edge cases

- Again brings a card back into practice; known cards leave the current pass.
