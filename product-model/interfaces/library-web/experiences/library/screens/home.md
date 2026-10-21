---
entities:
- entity: lecture
  shows:
  - Title
  - Class
  - Date
  - Transcript
  - Study notes
  - Topics
  - Filed copy
- entity: class
  shows:
  - Name
  - Group
  - Lecture count
references:
- kind: code
  role: implementation
  target: engine/src/StudyStash.App/Shell.Overview.cs
- kind: code
  role: implementation
  target: engine/src/StudyStash.Core/ClaudeTools.cs
- kind: code
  role: implementation
  target: engine/src/StudyStash.Core/LibraryReader.cs
- kind: code
  role: implementation
  target: engine/src/StudyStash.Core/Store.cs
- kind: code
  role: implementation
  target: ios/StudyStash/Screens/Library/LibraryTab.swift
- kind: code
  role: implementation
  target: ios/StudyStash/Screens/Search/SearchViews.swift
- kind: code
  role: implementation
  target: web/src/screens/Home.tsx
- kind: code
  role: implementation
  target: web/src/screens/Search.tsx
---

# Library

The library’s web home: the classes and the filed lectures, with search.
