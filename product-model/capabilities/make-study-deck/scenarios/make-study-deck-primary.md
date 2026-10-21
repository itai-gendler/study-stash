---
kind: primary
routes:
  phone-web-library: Phone web app
  ios-library: iPhone and iPad app
steps:
- text: The student asks for flashcards and a quiz.
  kind: actor
  actor: student
  entities: []
  contexts: &id001
    phone-web-library:
      place: phone-web::library::study
    ios-library:
      place: ios::library::study
- text: The Product reads the lecture and keeps a generated study deck.
  kind: product
  entities:
  - entity: lecture
    effect: reads
    facts:
    - Title
    - Study notes
  - entity: study-deck
    effect: creates
    facts:
    - Cards
    - Quiz
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

# Make flashcards and quiz

## Trigger

The student wants to practise a lecture on the phone.

## Outcome

Flashcards and quiz questions made from the lecture’s notes are kept on the phone.

## Edge cases

- If the answer contains no usable cards or quiz questions, the page reports a problem and offers to try again.
- Generating a new set replaces the locally saved set for this lecture.
