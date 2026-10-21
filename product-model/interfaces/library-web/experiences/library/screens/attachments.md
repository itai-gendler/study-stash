---
entities:
- entity: attachment
  shows:
  - Name
  - Kind
  - Size
  - Added
  - Text
  - Used in notes
- entity: class
  shows:
  - Name
- entity: lecture
  shows:
  - Title
references:
- kind: code
  role: implementation
  target: engine/src/StudyStash.App/ViewModels/AttachmentsModel.cs
- kind: code
  role: implementation
  target: engine/src/StudyStash.Core/Attachments.cs
- kind: code
  role: implementation
  target: engine/src/StudyStash.Core/ClaudeTools.cs
- kind: code
  role: implementation
  target: engine/src/StudyStash.Core/Store.Attachments.cs
- kind: code
  role: implementation
  target: engine/src/StudyStash.Library/LibraryWeb.Attachments.cs
- kind: code
  role: implementation
  target: ios/StudyStash/Screens/Add/AddFilesView.swift
- kind: code
  role: implementation
  target: ios/StudyStash/Screens/Library/ClassView.swift
- kind: code
  role: implementation
  target: web/src/screens/Upload.tsx
- kind: code
  role: implementation
  target: web/src/screens/attachments.tsx
---

# Attachments

The files attached to a lecture or class, in the library’s web pages.
