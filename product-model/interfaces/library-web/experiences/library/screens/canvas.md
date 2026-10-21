---
entities:
- entity: assignment
  shows:
  - Title
  - Due
  - Status
  - Instructions
  - Rubric
  - Submission
  - Feedback
  - Link
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
- entity: class
  shows:
  - Canvas course
  - Modules
- entity: canvas-connection
  shows:
  - School
  - Browser
  - Courses
  - Last sync
  - Problem
references:
- kind: code
  role: implementation
  target: engine/src/StudyStash.App/ViewModels/CanvasConnectModel.cs
- kind: code
  role: implementation
  target: engine/src/StudyStash.App/ViewModels/CanvasSettingsModel.cs
- kind: code
  role: implementation
  target: engine/src/StudyStash.Core/Canvas/CanvasSettings.cs
- kind: code
  role: implementation
  target: engine/src/StudyStash.Core/Canvas/CanvasSync.cs
- kind: code
  role: implementation
  target: engine/src/StudyStash.Core/Canvas/Crawl.cs
- kind: code
  role: implementation
  target: engine/src/StudyStash.Library/LibraryWeb.Canvas.cs
---

# Canvas

Canvas settings in the library’s web pages: the school, the browser, and the courses matched to classes.
