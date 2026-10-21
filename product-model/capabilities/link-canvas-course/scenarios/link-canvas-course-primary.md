---
kind: primary
routes:
  desktop: Desktop app
  library-web-library: Library web
steps:
- text: The student matches a Canvas course to one of their classes.
  kind: actor
  actor: student
  entities: []
  contexts: &id001
    desktop:
      place: desktop::canvas
    library-web-library:
      place: library-web::library::canvas
- text: The Product links the class to the selected course.
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
  target: engine/src/StudyStash.App/ViewModels/CanvasConnectModel.cs
---

# Link Canvas course

## Trigger

A course found by Find my courses belongs with a class.

## Outcome

That course’s work, modules, files, pages and announcements are synced into the class.

## Edge cases

- A newly selected course may create its class before linking it.
