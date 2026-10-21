---
kind: validation
routes:
  desktop: Desktop app
steps:
- text: The student stops a new capture lasting less than five seconds, with no student text.
  kind: actor
  actor: student
  entities: []
  contexts: &id001
    desktop:
      place: desktop::recording
- text: The Product removes the short recording.
  kind: product
  entities:
  - entity: recording
    effect: removes
    from: Recording
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

# Discard an accidental empty start

## Trigger

The student stops a new capture lasting less than five seconds, with no student text.

## Outcome

The accidental recording is not kept.
