---
kind: primary
routes:
  phone-web-library: Phone web app
  ios-library: iPhone and iPad app
steps:
- text: The student picks an answer for each item of the quiz.
  kind: actor
  actor: student
  entities: []
  contexts: &id001
    phone-web-library:
      place: phone-web::library::study
    ios-library:
      place: ios::library::study
- text: The Product checks answers against the study deck quiz and updates the session score.
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

# Answer quiz

## Trigger

The student wants to test themselves on a lecture.

## Outcome

Each answer is checked and explained, and the score for this attempt is shown.

## Edge cases

- Restarting resets the current attempt while keeping the generated questions.
