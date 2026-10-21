---
kind: primary
routes:
  desktop: Desktop app
steps:
- text: The student chooses Record, or presses its shortcut, with or without a class picked.
  kind: actor
  actor: student
  entities:
  - entity: class
    effect: reads
    facts: []
  contexts:
    desktop:
      place: desktop::recording
- text: The Product begins a recording and opens its page.
  kind: product
  entities:
  - entity: recording
    effect: creates
    facts:
    - Title
    - Class
    - Started
    - Duration
    - Audio
    - Transcript
    - Your notes
    - Timing
    - Calendar event
    - Delivery
    to: Recording
  contexts:
    desktop:
      place: desktop::recording
  actor: student
references:
- kind: code
  role: implementation
  target: engine/src/StudyStash.App/Shell.Recording.cs
- kind: code
  role: implementation
  target: engine/src/StudyStash.Core/Recording/Recorder.cs
- kind: code
  role: implementation
  target: ios/StudyStash/Recording/Recorder.swift
---

# Record on the computer

## Trigger

The student starts recording with a class selected or leaves the class undecided.

## Outcome

The recording is saved locally and its lecture page opens for typing.
