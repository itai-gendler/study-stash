---
kind: primary
routes:
  ios-library: iPhone and iPad app
steps:
- text: The student names the native capture.
  kind: actor
  actor: student
  entities: []
  contexts: &id001
    ios-library:
      place: ios::library::recording
- text: The Product changes the phone recording title.
  kind: product
  entities:
  - entity: phone-recording
    effect: changes
    facts:
    - Title
  contexts: *id001
  actor: student
references:
- kind: code
  role: implementation
  target: engine/src/StudyStash.App/Services/AppHost.cs
- kind: code
  role: implementation
  target: engine/src/StudyStash.App/Shell.Recording.cs
- kind: code
  role: implementation
  target: ios/StudyStash/Recording/RecordView.swift
---

# Name on the phone

## Trigger

The student names the native capture.

## Outcome

The title is sent as a student choice.
