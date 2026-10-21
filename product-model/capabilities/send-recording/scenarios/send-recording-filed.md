---
kind: primary
routes:
  desktop: Desktop app
steps:
- text: The library reports a completed desktop delivery.
  kind: condition
  unattended: true
  entities: []
  contexts: &id001
    desktop:
      place: desktop::recording
- text: The Product marks the recording filed with the library’s result.
  kind: product
  entities:
  - entity: recording
    effect: changes
    facts:
    - Delivery
    from: Writing
    to: Filed
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

# Follow the finished write-up

## Trigger

The library reports a completed desktop delivery.

## Outcome

The desktop knows the filed title and class.
