---
kind: primary
routes:
  ios-library: iPhone and iPad app
steps:
- text: The student chooses Resume in the native recorder.
  kind: actor
  actor: student
  entities: []
  contexts: &id001
    ios-library:
      place: ios::library::recording
- text: The Product resumes capture for the phone recording.
  kind: product
  entities:
  - entity: phone-recording
    effect: changes
    facts:
    - Audio
    - Duration
  contexts: *id001
  actor: student
references:
- kind: code
  role: implementation
  target: engine/src/StudyStash.Core/Recording/Recorder.cs
- kind: code
  role: implementation
  target: ios/StudyStash/Recording/Recorder.swift
---

# Resume on the phone

## Trigger

The student chooses Resume in the native recorder.

## Outcome

New sound continues the same phone recording.
