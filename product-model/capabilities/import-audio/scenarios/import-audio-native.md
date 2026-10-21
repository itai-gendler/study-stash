---
kind: primary
routes:
  ios-library: iPhone and iPad app
steps:
- text: The student imports audio into the native app.
  kind: actor
  actor: student
  entities: []
  contexts: &id001
    ios-library:
      place: ios::library::voice-memos
- text: The Product recognizes the file and keeps a phone recording ready to send.
  kind: product
  entities:
  - entity: phone-recording
    effect: creates
    facts:
    - Title
    - Class
    - Started
    - Duration
    - Audio
    - Transcript
    - Your notes
    - Problem
    to: Waiting
  contexts: *id001
  actor: student
references:
- kind: code
  role: implementation
  target: web/src/screens/VoiceMemo.tsx
- kind: code
  role: implementation
  target: ios/StudyStash/Recording/ImportAudioView.swift
- kind: code
  role: implementation
  target: engine/src/StudyStash.Library/LibraryWeb.VoiceMemos.cs
- kind: code
  role: implementation
  target: engine/src/StudyStash.Library/VoiceMemos.cs
---

# Transcribe an imported file on the phone

## Trigger

The student imports audio into the native app.

## Outcome

The recognized words are retained locally for ordinary delivery.
