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
- kind: code
  role: implementation
  target: web/src/screens/VoiceMemo.tsx
---

# Imported audio

Sending a sound file from the phone web app, with a title and class, and the imports waiting, failed or done.
