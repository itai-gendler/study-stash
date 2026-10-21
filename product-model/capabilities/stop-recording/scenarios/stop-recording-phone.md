---
kind: primary
routes:
  ios-library: iPhone and iPad app
steps:
- text: The student stops the native recorder.
  kind: actor
  actor: student
  entities: []
  contexts: &id001
    ios-library:
      place: ios::library::recording
- text: The Product finishes the last words and keeps the phone recording.
  kind: product
  entities:
  - entity: phone-recording
    effect: changes
    facts:
    - Audio
    - Duration
    - Transcript
    from: Recording
    to: Waiting
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

# Finish a phone recording

## Trigger

The student stops the native recorder.

## Outcome

The phone recording retains its final recognized words and waits to send.
