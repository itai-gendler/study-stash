---
kind: primary
routes:
  desktop: Desktop app
steps:
- text: The student types notes while the computer records.
  kind: actor
  actor: student
  entities: []
  contexts: &id001
    desktop:
      place: desktop::recording
- text: The Product keeps the student’s text on the recording.
  kind: product
  entities:
  - entity: recording
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

# Keep typing on the recording page

## Trigger

The student types notes while the computer records.

## Outcome

The typed words are kept independently and travel with the transcript.
