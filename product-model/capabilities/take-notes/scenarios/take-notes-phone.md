---
kind: primary
routes:
  ios-library: iPhone and iPad app
steps:
- text: The student types during a native phone recording.
  kind: actor
  actor: student
  entities:
  - entity: phone-recording
    effect: reads
    facts: []
  contexts: &id001
    ios-library:
      place: ios::library::recording
- text: The Product keeps text on the phone recording.
  kind: product
  entities:
  - entity: phone-recording
    effect: changes
    facts:
    - Your notes
  contexts: *id001
  actor: student
references:
- kind: code
  role: implementation
  target: engine/src/StudyStash.App/Shell.Recording.cs
- kind: code
  role: implementation
  target: ios/StudyStash/Recording/RecordView.swift
---

# Keep typing on the phone

## Trigger

The student types during a native recording.

## Outcome

The phone recording keeps the student’s text for delivery.
