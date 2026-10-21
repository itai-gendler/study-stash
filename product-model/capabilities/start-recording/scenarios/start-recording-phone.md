---
kind: primary
routes:
  ios-library: iPhone and iPad app
steps:
- text: The student chooses Record in the iPhone or iPad app, with or without a class picked.
  kind: actor
  actor: student
  entities:
  - entity: class
    effect: reads
    facts: []
  contexts:
    ios-library:
      place: ios::library::recording
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
    ios-library:
      place: ios::library::recording
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

# Record on iPhone or iPad

## Trigger

The student starts recording in the native app.

## Outcome

The phone recording retains audio and begins recognizing timed speech on the device.
