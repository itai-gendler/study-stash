---
kind: primary
routes:
  ai-apps: AI apps
steps:
- text: The connected AI app requests class materials.
  kind: actor
  actor: ai-agent
  entities:
  - entity: class
    effect: reads
    facts: []
  contexts: &id001
    ai-apps:
      place: ai-apps
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
  actor: ai-agent
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

The connected AI app requests class materials.

## Outcome

The class’s ordered modules and material are available; locked or unavailable entries explain their status.
