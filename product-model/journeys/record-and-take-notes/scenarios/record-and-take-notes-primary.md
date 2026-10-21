---
kind: primary
result: achieved
routes:
  main: Keep personal notes with a recording
steps:
- text: The student chooses Record, or presses its shortcut, with or without a class picked.
  kind: actor
  actor: student
  entities:
  - entity: class
    effect: reads
    facts: []
  contexts:
    main:
      place: desktop::recording
  capability: start-recording
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
    main:
      place: desktop::recording
  actor: student
  capability: start-recording
- text: The student types notes while the computer records.
  kind: actor
  actor: student
  entities: []
  contexts:
    main:
      place: desktop::recording
  capability: take-notes
- text: The Product keeps the student’s text on the recording.
  kind: product
  entities:
  - entity: recording
    effect: changes
    facts:
    - Your notes
  contexts:
    main:
      place: desktop::recording
  actor: student
  capability: take-notes
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
- kind: code
  role: implementation
  target: ios/StudyStash/Recording/RecordView.swift
---

# Keep personal notes with a recording

## Trigger

The student starts a desktop lecture and is taken to its recording page.

## Outcome

The recording holds the words the student types on that page.
