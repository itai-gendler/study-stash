---
kind: primary
routes:
  desktop: Desktop app
steps:
- text: The student chooses Resume.
  kind: actor
  actor: student
  entities: []
  contexts: &id001
    desktop:
      place: desktop::recording
- text: The Product resumes the recording.
  kind: product
  entities:
  - entity: recording
    effect: changes
    facts:
    - Audio
    - Duration
    from: Paused
    to: Recording
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

# Resume on the computer

## Trigger

The student chooses Resume.

## Outcome

New sound is added to the same recording.
