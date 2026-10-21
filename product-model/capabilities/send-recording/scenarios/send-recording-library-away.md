---
kind: edge
routes:
  desktop: Desktop app
steps:
- text: A delivery attempt cannot reach the library.
  kind: condition
  unattended: true
  entities: []
  contexts: &id001
    desktop:
      place: desktop::recording
- text: The Product keeps the recording and reports the delivery problem.
  kind: product
  entities:
  - entity: recording
    effect: changes
    facts:
    - Delivery
  contexts: *id001
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

# Keep a desktop delivery waiting

## Trigger

A delivery attempt cannot reach the library.

## Outcome

The recording remains Sending and retries later; reconnecting prompts another attempt.
