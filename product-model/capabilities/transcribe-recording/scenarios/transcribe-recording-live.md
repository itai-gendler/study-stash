---
kind: primary
routes:
  desktop: Desktop app
steps:
- text: The student watches the recorder while it transcribes as it goes.
  kind: actor
  actor: student
  entities: []
  contexts: &id001
    desktop:
      place: desktop::recording
- text: The Product adds timed words to the recording while capture continues.
  kind: product
  entities:
  - entity: recording
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

# Read words during capture

## Trigger

Transcription as it goes is on, and the student watches the recorder during the lecture.

## Outcome

Words appear during the recording, and Ask can use the available transcript.

## Decision points

### Transcription pace

Which local text is ready?

- The live recognizer keeps up → show its immediate words.
- Live words are unavailable or fall behind → show the main transcript as its pieces arrive.
