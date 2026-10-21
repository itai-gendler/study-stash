---
kind: validation
routes:
  ios-library: iPhone and iPad app
steps:
- text: The student chooses Send now for a phone recording with no transcript.
  kind: actor
  actor: student
  entities:
  - entity: phone-recording
    effect: reads
    facts: []
  contexts: &id001
    ios-library:
      place: ios::library::recording
- text: The Product retains the phone recording with its problem.
  kind: product
  entities:
  - entity: phone-recording
    effect: changes
    facts:
    - Problem
    from: Waiting
    to: Failed
  contexts: *id001
  actor: student
references:
- kind: code
  role: implementation
  target: engine/src/StudyStash.Core/Recording/Recorder.cs
- kind: code
  role: implementation
  target: ios/StudyStash/Recording/Recording.swift
- kind: code
  role: implementation
  target: engine/src/StudyStash.Library/LibraryWeb.PhoneLectures.cs
---

# Keep a recording without recognized words

## Trigger

The student chooses Send now for a phone recording with no transcript.

## Outcome

The recording stays on the device and says nothing was heard.
