---
kind: primary
routes:
  desktop: Desktop app
  library-web-library: Library web
steps:
- text: The student changes the school’s Canvas address or the browser that reads Canvas.
  kind: actor
  actor: student
  entities: []
  contexts: &id001
    desktop:
      place: desktop::canvas
    library-web-library:
      place: library-web::library::canvas
- text: The Product changes the Canvas connection settings.
  kind: product
  entities:
  - entity: canvas-connection
    effect: changes
    facts:
    - School
    - Browser
  contexts: *id001
  actor: student
references:
- kind: code
  role: implementation
  target: engine/src/StudyStash.App/ViewModels/CanvasSettingsModel.cs
- kind: code
  role: implementation
  target: engine/src/StudyStash.Library/LibraryWeb.Canvas.cs
- kind: code
  role: implementation
  target: engine/src/StudyStash.Core/Canvas/CanvasSync.cs
---

# Change Canvas settings

## Trigger

The school’s Canvas address changed, or the student wants another browser to read Canvas.

## Outcome

Canvas is read from the new address through the chosen browser.
