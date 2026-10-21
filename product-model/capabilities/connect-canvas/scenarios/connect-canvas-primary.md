---
kind: primary
routes:
  desktop: Desktop app
  library-web-library: Library web
steps:
- text: The student gives the school’s Canvas address, connects the Study Stash for Canvas browser extension with the code shown, and chooses Find my courses.
  kind: actor
  actor: student
  entities: []
  contexts: &id001
    desktop:
      place: desktop::canvas
    library-web-library:
      place: library-web::library::canvas
- text: The Product saves the Canvas connection and lists the available courses.
  kind: product
  entities:
  - entity: canvas-connection
    effect: changes
    facts:
    - School
    - Browser
    - Courses
    - Problem
  contexts: *id001
  actor: student
references:
- kind: code
  role: implementation
  target: engine/src/StudyStash.App/ViewModels/CanvasConnectModel.cs
- kind: code
  role: implementation
  target: engine/src/StudyStash.Library/LibraryWeb.Canvas.cs
- kind: code
  role: implementation
  target: engine/src/StudyStash.Core/Canvas/CanvasSync.cs
---

# Connect Canvas

## Trigger

The student wants their Canvas work next to their lectures.

## Outcome

Canvas is read through the student’s own browser sign-in, and their courses are listed to match with classes.

## Edge cases

- If the browser is not signed in, the connection explains where to sign in.
- If multiple browsers are present, the student can choose which one reads Canvas.
