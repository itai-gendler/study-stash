---
kind: primary
routes:
  ios-library: iPhone and iPad app
steps:
- text: A stopped phone recording with recognized words is waiting and the library is reachable.
  kind: condition
  unattended: true
  entities:
  - entity: phone-recording
    effect: reads
    facts: []
  contexts: &id001
    ios-library:
      place: ios::library::recording
- text: The Product starts sending the phone recording.
  kind: product
  entities:
  - entity: phone-recording
    effect: changes
    facts:
    - Problem
    from: Waiting
    to: Sending
  contexts: *id001
- text: The Product accepts the lecture and marks the phone recording sent.
  kind: product
  entities:
  - entity: lecture
    effect: creates
    facts:
    - Title
    - Class
    - Date
    - Recorder
    - Duration
    - Transcript
    - Your notes
    - Study notes
    - Writer
    - Topics
    - Filing choice
    - Problem
    - Filed copy
    to: Queued
  - entity: phone-recording
    effect: changes
    facts:
    - Problem
    from: Sending
    to: Sent
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

# Send from the native app

## Trigger

A stopped phone recording with recognized words is waiting and the library is reachable.

## Outcome

The library has the lecture for processing and the phone keeps its local recording.
