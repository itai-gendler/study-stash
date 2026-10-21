---
references:
- kind: code
  role: implementation
  target: engine/src/StudyStash.Core/Canvas/CanvasIndex.cs
- kind: code
  role: implementation
  target: engine/src/StudyStash.App/ViewModels/CanvasClassModel.cs
- kind: code
  role: implementation
  target: engine/src/StudyStash.App/ViewModels/CanvasReaderModel.cs
---

# Course material

An addressable page or file mirrored from Canvas. The common facts describe the material the student opens; module ordering lives on the class.

## Information kept

- **Title** — The name of the material.
- **Kind** — File, page, quiz or discussion introduction.
- **Content** — The readable text or locally saved original.
- **Source** — Its course, author or Canvas address when supplied.
- **Availability** — Whether the material is saved, unavailable or locked in Canvas.
