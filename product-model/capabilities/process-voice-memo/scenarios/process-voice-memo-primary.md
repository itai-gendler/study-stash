---
kind: primary
routes:
  phone-web-library: Phone web app
  ios-library: iPhone and iPad app
  desktop: Desktop app
steps:
- text: A capture computer finds a waiting imported audio file.
  kind: condition
  unattended: true
  entities: []
  contexts: &id001
    phone-web-library:
      place: phone-web::library::voice-memos
    ios-library:
      place: ios::library::voice-memos
    desktop:
      place: desktop
- text: The Product claims the voice memo for a capture computer.
  kind: product
  entities:
  - entity: voice-memo
    effect: changes
    facts:
    - Computer
    from: Waiting
    to: Transcribing
  contexts: *id001
- text: The Product prepares a recording for transcription.
  kind: product
  entities:
  - entity: recording
    effect: creates
    facts:
    - Title
    - Class
    - Started
    - Duration
    - Audio
    - Transcript
    - Your notes
    - Timing
    - Calendar event
    - Delivery
    to: Transcribing
  contexts: *id001
- text: The Product marks the voice memo imported and releases the uploaded original.
  kind: product
  entities:
  - entity: voice-memo
    effect: changes
    facts:
    - Lecture
    from: Transcribing
    to: Done
  contexts: *id001
references:
- kind: code
  role: implementation
  target: engine/src/StudyStash.Core/Recording/VoiceMemoImport.cs
- kind: code
  role: implementation
  target: engine/src/StudyStash.Library/VoiceMemos.cs
---

# Process imported audio

## Trigger

A recording computer finds a waiting imported audio file.

## Outcome

The imported audio is a local recording; transcript delivery and library filing follow through the normal queue.

## Edge cases

- An expired claim becomes available to another recording computer.
