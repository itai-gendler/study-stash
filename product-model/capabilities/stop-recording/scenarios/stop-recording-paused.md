---
kind: primary
routes:
  desktop: Desktop app
steps:
- text: The student stops a paused session.
  kind: actor
  actor: student
  entities: []
  contexts: &id001
    desktop:
      place: desktop::recording
- text: The Product ends the paused recording.
  kind: product
  entities:
  - entity: recording
    effect: changes
    facts:
    - Audio
    - Duration
    from: Paused
    to: Transcribing
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

# Finish while paused

## Trigger

The student stops a paused session.

## Outcome

The captured sound proceeds to transcription.
