---
entities:
- entity: voice-memo
  shows:
  - Name
  - Title
  - Class
  - Added
  - Size
  - Computer
  - Lecture
  - Problem
- entity: phone-recording
  shows:
  - Title
  - Class
  - Started
  - Duration
  - Audio
  - Transcript
  - Your notes
  - Problem
- entity: recording
  shows:
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
references:
- kind: code
  role: implementation
  target: engine/src/StudyStash.Core/Recording/VoiceMemoImport.cs
- kind: code
  role: implementation
  target: engine/src/StudyStash.Library/LibraryWeb.Phone.cs
- kind: code
  role: implementation
  target: engine/src/StudyStash.Library/VoiceMemos.cs
- kind: code
  role: implementation
  target: ios/StudyStash/Recording/ImportAudioView.swift
- kind: code
  role: implementation
  target: web/src/screens/Upload.tsx
---

# Imported audio

Importing a sound file on iPhone or iPad, with a title and class, and imports waiting for a computer.
