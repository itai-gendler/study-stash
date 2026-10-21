---
kind: primary
routes:
  desktop: Desktop app
steps:
- text: The student chooses Pause.
  kind: actor
  actor: student
  entities: []
  contexts: &id001
    desktop:
      place: desktop::recording
- text: The Product pauses the recording.
  kind: product
  entities:
  - entity: recording
    effect: changes
    facts:
    - Duration
    from: Recording
    to: Paused
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

# Pause on the computer

## Trigger

The student chooses Pause.

## Outcome

The recording is paused and keeps the sound already captured.
