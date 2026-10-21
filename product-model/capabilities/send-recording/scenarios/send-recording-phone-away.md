---
kind: edge
routes:
  ios-library: iPhone and iPad app
steps:
- text: The native app cannot reach the library while sending.
  kind: condition
  unattended: true
  entities: []
  contexts: &id001
    ios-library:
      place: ios::library::recording
- text: The Product returns the phone recording to waiting.
  kind: product
  entities:
  - entity: phone-recording
    effect: changes
    facts:
    - Problem
    from: Sending
    to: Waiting
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

# Keep a phone delivery waiting

## Trigger

The native app cannot reach the library while sending.

## Outcome

The phone recording returns to Waiting and is tried when the app comes back.
