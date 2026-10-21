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
  target: engine/src/StudyStash.Core/Store.cs
- kind: code
  role: implementation
  target: engine/src/StudyStash.App/Shell.Overview.cs
- kind: code
  role: implementation
  target: web/src/screens/Home.tsx
- kind: code
  role: implementation
  target: web/src/screens/Search.tsx
- kind: code
  role: implementation
  target: ios/StudyStash/Screens/Library/LibraryTab.swift
- kind: code
  role: implementation
  target: ios/StudyStash/Screens/Search/SearchViews.swift
- kind: code
  role: implementation
  target: engine/src/StudyStash.Core/ClaudeTools.cs
---

# Browse library

Browse all filed lectures, a class or Unsorted, and find matching titles, topics and passages by searching.
