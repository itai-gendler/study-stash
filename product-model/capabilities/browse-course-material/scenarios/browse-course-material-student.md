---
kind: primary
routes:
  desktop: Desktop app
  library-web-library: Library web
steps:
- text: The student opens the class material.
  kind: actor
  actor: student
  entities:
  - entity: class
    effect: reads
    facts: []
  contexts: &id001
    desktop:
      place: desktop::class
    library-web-library:
      place: library-web::library::class
- text: The Product presents the class modules and course material.
  kind: product
  entities:
  - entity: class
    effect: reads
    facts:
    - Name
    - Modules
  - entity: course-material
    effect: reads
    facts:
    - Title
    - Kind
    - Content
    - Source
    - Availability
  - entity: announcement
    effect: reads
    facts:
    - Title
    - Body
    - Author
    - Posted
    - Source
    - New
  contexts: *id001
  actor: student
references:
- kind: code
  role: implementation
  target: engine/src/StudyStash.App/ViewModels/CanvasClassModel.cs
- kind: code
  role: implementation
  target: engine/src/StudyStash.App/ViewModels/CanvasReaderModel.cs
- kind: code
  role: implementation
  target: engine/src/StudyStash.Library/LibraryWeb.Canvas.cs
- kind: code
  role: implementation
  target: engine/src/StudyStash.Core/ClaudeTools.cs
---

# Read class materials

## Trigger

The student opens the class material.

## Outcome

The class’s ordered modules and material are available; locked or unavailable entries explain their status.
