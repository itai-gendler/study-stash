---
kind: primary
result: achieved
routes:
  phone: iPhone and iPad app
steps:
- text: The student chooses Record in the iPhone or iPad app, with or without a class picked.
  kind: actor
  actor: student
  entities:
  - entity: class
    effect: reads
    facts: []
  contexts:
    phone:
      place: ios::library::recording
  capability: start-recording
- text: The Product starts a phone recording with the device’s speech language.
  kind: product
  entities:
  - entity: phone-recording
    effect: creates
    facts:
    - Title
    - Class
    - Started
    - Duration
    - Audio
    - Transcript
    - Your notes
    - Problem
    to: Recording
  contexts:
    phone:
      place: ios::library::recording
  actor: student
  capability: start-recording
- text: The student types during a native phone recording.
  kind: actor
  actor: student
  entities:
  - entity: phone-recording
    effect: reads
    facts: []
  contexts:
    phone:
      place: ios::library::recording
  capability: take-notes
- text: The Product keeps text on the phone recording.
  kind: product
  entities:
  - entity: phone-recording
    effect: changes
    facts:
    - Your notes
  contexts:
    phone:
      place: ios::library::recording
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

# Keep personal notes with a phone recording

## Trigger

The student starts a native capture and the app opens its recorder.

## Outcome

The phone recording keeps the words typed during capture.
