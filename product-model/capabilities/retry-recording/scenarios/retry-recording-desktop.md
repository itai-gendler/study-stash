---
kind: primary
routes:
  desktop: Desktop app
steps:
- text: The student chooses Try again for a failed desktop recording.
  kind: actor
  actor: student
  entities:
  - entity: recording
    effect: reads
    facts: []
  contexts: &id001
    desktop:
      place: desktop::recording
- text: The Product clears the recording problem and resumes transcription.
  kind: product
  entities:
  - entity: recording
    effect: changes
    facts:
    - Delivery
    from: Failed
    to: Transcribing
  contexts: *id001
  actor: student
references:
- kind: code
  role: implementation
  target: engine/src/StudyStash.Core/Recording/Recorder.cs
- kind: code
  role: implementation
  target: ios/StudyStash/Screens/Library/LibraryTab.swift
- kind: code
  role: implementation
  target: ios/StudyStash/Recording/Recording.swift
---

# Retry local recognition

## Trigger

The student chooses Try again for a failed desktop recording.

## Outcome

The unfinished transcription is attempted again.

## Edge cases

- If recognition is already complete, retry goes straight to delivery.
