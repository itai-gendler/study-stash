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
  target: engine/src/StudyStash.App/ViewModels/AttachmentsModel.cs
- kind: code
  role: implementation
  target: engine/src/StudyStash.Library/LibraryWeb.Attachments.cs
- kind: code
  role: implementation
  target: web/src/screens/attachments.tsx
- kind: code
  role: implementation
  target: ios/StudyStash/Screens/Library/ClassView.swift
- kind: code
  role: implementation
  target: engine/src/StudyStash.Core/ClaudeTools.cs
---

# Read attachment

Open the original file or read its extracted text.
