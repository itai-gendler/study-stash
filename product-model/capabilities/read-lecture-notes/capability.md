---
availability:
- place: desktop
- place: library-web::library
- place: phone-web::library
- place: ios::library
- place: ai-apps
references:
- kind: code
  role: implementation
  target: engine/src/StudyStash.Core/LibraryReader.cs
- kind: code
  role: implementation
  target: engine/src/StudyStash.Core/ClaudeTools.cs
- kind: code
  role: implementation
  target: engine/src/StudyStash.App/Shell.Library.cs
- kind: code
  role: implementation
  target: web/src/screens/LectureScreen.tsx
- kind: code
  role: implementation
  target: ios/StudyStash/Screens/Library/LectureView.swift
---

# Read lecture notes

Read the notes of one lecture, with its source and processing context.
