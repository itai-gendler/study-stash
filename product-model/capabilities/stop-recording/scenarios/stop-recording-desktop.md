---
kind: primary
routes:
  desktop: Desktop app
steps:
- text: The student stops a recording after at least five seconds.
  kind: actor
  actor: student
  entities:
  - entity: recording
    effect: reads
    facts: []
  contexts: &id001
    desktop:
      place: desktop::recording
- text: The Product ends the recording and retains its audio.
  kind: product
  entities:
  - entity: recording
    effect: changes
    facts:
    - Audio
    - Duration
    from: Recording
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

# Finish a computer recording

## Trigger

The student stops a recording after at least five seconds.

## Outcome

The remaining sound is queued for transcription.
