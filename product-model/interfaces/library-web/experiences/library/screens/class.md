---
entities:
- entity: class
  shows:
  - Name
  - Modules
- entity: course-material
  shows:
  - Title
  - Kind
  - Content
  - Source
  - Availability
- entity: announcement
  shows:
  - Title
  - Body
  - Author
  - Posted
  - Source
  - New
references:
- kind: code
  role: implementation
  target: engine/src/StudyStash.App/ViewModels/CanvasClassModel.cs
- kind: code
  role: implementation
  target: engine/src/StudyStash.App/ViewModels/CanvasReaderModel.cs
- kind: code
  role: implementation
  target: engine/src/StudyStash.Core/ClaudeTools.cs
- kind: code
  role: implementation
  target: engine/src/StudyStash.Library/LibraryWeb.Canvas.cs
---

# Class

A class in the library’s web pages, with its Canvas modules, files, pages and announcements.
