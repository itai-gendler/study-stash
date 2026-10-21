---
kind: primary
routes:
  phone-web-library: Phone web app
steps:
- text: The student selects an audio file in the phone web app.
  kind: actor
  actor: student
  entities: []
  contexts: &id001
    phone-web-library:
      place: phone-web::library::voice-memos
- text: The Product keeps a voice memo for import.
  kind: product
  entities:
  - entity: voice-memo
    effect: creates
    facts:
    - Name
    - Title
    - Class
    - Added
    - Size
    - Computer
    - Lecture
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

# Send audio for computer transcription

## Trigger

The student selects an audio file in the phone web app.

## Outcome

The upload waits for a recording computer.

## Edge cases

- Audio uploads are limited to 500 MB and supported sound-file extensions.
