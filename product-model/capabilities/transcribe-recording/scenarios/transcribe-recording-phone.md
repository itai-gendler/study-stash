---
kind: primary
routes:
  ios-library: iPhone and iPad app
steps:
- text: The student watches the native recorder.
  kind: actor
  actor: student
  entities: []
  contexts: &id001
    ios-library:
      place: ios::library::recording
- text: The Product adds timed words to the phone recording.
  kind: product
  entities:
  - entity: phone-recording
    effect: changes
    facts:
    - Transcript
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

# Recognize speech on the phone

## Trigger

The student watches the native recorder.

## Outcome

Final recognized segments are kept on the device.
