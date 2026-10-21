---
kind: primary
routes:
  desktop: Desktop app
  library-web-library: Library web
steps:
- text: The student unlinks a Canvas course.
  kind: actor
  actor: student
  entities: []
  contexts: &id001
    desktop:
      place: desktop::canvas
    library-web-library:
      place: library-web::library::canvas
- text: The Product removes the class’s Canvas course link.
  kind: product
  entities:
  - entity: class
    effect: changes
    facts:
    - Canvas course
  - entity: canvas-connection
    effect: changes
    facts:
    - Courses
  contexts: *id001
  actor: student
references:
- kind: code
  role: implementation
  target: engine/src/StudyStash.Library/LibraryWeb.Canvas.cs
- kind: code
  role: implementation
  target: engine/src/StudyStash.Core/Canvas/CanvasSettings.cs
---

# Unlink Canvas course

## Trigger

A class should no longer bring in a Canvas course.

## Outcome

The course is no longer synced into that class.
