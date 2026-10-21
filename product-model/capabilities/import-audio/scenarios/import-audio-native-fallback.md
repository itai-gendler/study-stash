---
kind: alternate
routes:
  ios-library: iPhone and iPad app
steps:
- text: The student imports a sound file into the iPhone or iPad app, with a title.
  kind: actor
  actor: student
  entities: []
  contexts:
    ios-library:
      place: ios::library::voice-memos
- text: The device cannot provide the speech model needed for the file.
  kind: condition
  actor: student
  entities: []
  contexts:
    ios-library:
      place: ios::library::voice-memos
- text: The Product sends the sound file to the library to be imported by a computer.
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
  contexts:
    ios-library:
      place: ios::library::voice-memos
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

# Send audio when native recognition is unavailable

## Trigger

The student imports a sound file on a device that cannot recognise its speech itself.

## Outcome

The library holds the sound until a recording computer can process it.
