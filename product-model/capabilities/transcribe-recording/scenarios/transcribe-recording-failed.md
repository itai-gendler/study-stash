---
kind: edge
routes:
  desktop: Desktop app
steps:
- text: The desktop worker cannot read the audio or repeated recognition attempts fail.
  kind: condition
  unattended: true
  entities: []
  contexts: &id001
    desktop:
      place: desktop::recording
- text: The Product marks the recording as failed.
  kind: product
  entities:
  - entity: recording
    effect: changes
    facts:
    - Delivery
    from: Transcribing
    to: Failed
  contexts: *id001
references:
- kind: code
  role: implementation
  target: engine/src/StudyStash.Core/Recording/Recorder.cs
- kind: code
  role: implementation
  target: ios/StudyStash/Recording/Recorder.swift
---

# A stopped recording cannot be transcribed

## Trigger

The desktop worker cannot read the audio or repeated recognition attempts fail.

## Outcome

The recording is retained with a problem for retry.
