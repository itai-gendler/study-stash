---
availability:
- place: phone-web::library
- place: ios::library
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

# Import a recording

Bring an existing sound file into the lecture pipeline, with a title and optional class.
