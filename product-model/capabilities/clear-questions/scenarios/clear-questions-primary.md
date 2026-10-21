---
kind: primary
routes:
  phone-web-library: phone-web-library
  ios-library: ios-library
steps:
- text: The student chooses Clear in Ask.
  kind: actor
  actor: student
  entities: []
  contexts: &id001
    phone-web-library:
      place: phone-web::library::ask
    ios-library:
      place: ios::library::ask
- text: The Product removes the locally saved question history.
  kind: product
  actor: student
  entities:
  - entity: question
    effect: removes
    from: Answered
  contexts: *id001
references:
- kind: code
  role: implementation
  target: web/src/screens/Ask.tsx
- kind: code
  role: implementation
  target: ios/StudyStash/Screens/Ask/AskViews.swift
---

# Clear questions

## Trigger

The student chooses Clear in Ask.

## Outcome

Recent questions disappear from this device; library lectures and saved chats remain.

## Edge cases

- Failed or interrupted requests are cleared along with completed answers.
