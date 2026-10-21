---
kind: primary
routes:
  ios-library: iPhone and iPad app
steps:
- text: The student chooses Pause in the native recorder.
  kind: actor
  actor: student
  entities: []
  contexts: &id001
    ios-library:
      place: ios::library::recording
- text: The Product pauses capture and keeps the phone recording duration.
  kind: product
  entities:
  - entity: phone-recording
    effect: changes
    facts:
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

# Pause on the phone

## Trigger

The student chooses Pause in the native recorder.

## Outcome

Sound capture pauses; the phone recording remains the current session.
