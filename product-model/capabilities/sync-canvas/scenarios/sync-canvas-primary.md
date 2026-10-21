---
kind: primary
routes:
  desktop: Desktop app
  library-web-library: Library web
steps:
- text: The student chooses Sync now.
  kind: actor
  actor: student
  entities: []
  contexts: &id001
    desktop:
      place: desktop::canvas
    library-web-library:
      place: library-web::library::canvas
- text: The Product refreshes the assignment and course material mirror and the class module list.
  kind: product
  entities:
  - entity: assignment
    effect: creates
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
    effect: creates
    facts:
    - Title
    - Kind
    - Content
    - Source
    - Availability
  - entity: announcement
    effect: creates
    facts:
    - Title
    - Body
    - Author
    - Posted
    - Source
    - New
  - entity: class
    effect: changes
    facts:
    - Modules
  - entity: canvas-connection
    effect: changes
    facts:
    - Last sync
    - Problem
  contexts: *id001
  actor: student
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

# Sync Canvas

## Trigger

The student wants Canvas’s latest without waiting for the next sync.

## Outcome

Assignments with their rubrics, submissions and feedback, modules, files, pages and announcements are up to date in each linked class.

## Edge cases

- If the browser helper is away or signed out, the last mirrored material stays readable.
- Canvas asking the sync to slow down delays further work.
- Only the student’s available course material is mirrored.
