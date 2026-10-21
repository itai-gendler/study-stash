---
kind: edge
routes:
  desktop: Desktop app
  ios-library: iPhone and iPad app
steps:
- text: The student starts capture but the device cannot open the microphone.
  kind: actor
  actor: student
  entities: []
  contexts: &id001
    desktop:
      place: desktop::recording
    ios-library:
      place: ios::library::recording
- text: The Product explains the microphone problem and does not start capturing sound.
  kind: product
  entities: []
  contexts: *id001
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

# Microphone unavailable

## Trigger

The student starts capture but the device cannot open the microphone.

## Outcome

The app explains the microphone problem and capture does not start.
