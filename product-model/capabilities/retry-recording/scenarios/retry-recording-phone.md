---
kind: primary
routes:
  ios-library: iPhone and iPad app
steps:
- text: The student chooses Send now for a failed phone recording that has a transcript.
  kind: actor
  actor: student
  entities:
  - entity: phone-recording
    effect: reads
    facts: []
  contexts: &id001
    ios-library:
      place: ios::library::recording
- text: The Product retries sending the phone recording.
  kind: product
  entities:
  - entity: phone-recording
    effect: changes
    facts:
    - Problem
    from: Failed
    to: Sending
  contexts: *id001
  actor: student
- text: The Product marks the phone recording sent after acceptance.
  kind: product
  entities:
  - entity: phone-recording
    effect: changes
    facts:
    - Problem
    from: Sending
    to: Sent
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

# Retry native delivery

## Trigger

The student chooses Send now for a failed phone recording that has a transcript.

## Outcome

The stored transcript is sent without making a second lecture.
