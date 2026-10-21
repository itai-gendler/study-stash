---
kind: primary
routes:
  desktop: Desktop app
  library-web-library: Library web
steps:
- text: The browser helper checks in when the next course sync is due.
  kind: condition
  unattended: true
  entities: []
  contexts: &id001
    desktop:
      place: desktop::canvas
    library-web-library:
      place: library-web::library::canvas
- text: The Product refreshes assignment details, course material and connection progress.
  kind: product
  entities:
  - entity: assignment
    effect: changes
    facts:
    - Title
    - Due
    - Status
    - Instructions
    - Rubric
    - Submission
    - Feedback
    - Link
  - entity: course-material
    effect: changes
    facts:
    - Title
    - Kind
    - Content
    - Source
    - Availability
  - entity: announcement
    effect: changes
    facts:
    - Title
    - Body
    - Author
    - Posted
    - Source
    - New
  - entity: canvas-connection
    effect: changes
    facts:
    - Last sync
    - Problem
  contexts: *id001
references:
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

# Refresh Canvas in the background

## Trigger

The browser helper checks in when the next course sync is due.

## Outcome

The library refreshes its mirror and records the latest course changes.
