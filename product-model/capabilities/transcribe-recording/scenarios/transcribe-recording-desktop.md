---
kind: primary
routes:
  desktop: Desktop app
steps:
- text: A stopped recording has sound still to transcribe.
  kind: condition
  unattended: true
  entities:
  - entity: recording
    effect: reads
    facts: []
  contexts: &id001
    desktop:
      place: desktop::recording
- text: The Product adds recognized words and advances the recording to delivery.
  kind: product
  entities:
  - entity: recording
    effect: changes
    facts:
    - Transcript
    from: Transcribing
    to: Sending
  contexts: *id001
references:
- kind: code
  role: implementation
  target: engine/src/StudyStash.Core/Recording/Recorder.cs
- kind: code
  role: implementation
  target: ios/StudyStash/Recording/Recorder.swift
---

# Finish the desktop transcript

## Trigger

A stopped recording has sound still to transcribe.

## Outcome

The complete transcript is ready for delivery.

## Edge cases

- A model that cannot load leaves the sound waiting and reports why.
- Speaker labeling failure still permits delivery of the transcript.
