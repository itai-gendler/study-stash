---
kind: primary
routes:
  desktop: Desktop app
steps:
- text: The student chooses Disconnect next to a connected AI app.
  kind: actor
  actor: student
  entities: []
  contexts: &id001
    desktop:
      place: desktop::ai-apps
- text: The Product removes the AI app connection.
  kind: product
  entities:
  - entity: ai-connection
    effect: removes
  contexts: *id001
  actor: student
references:
- kind: code
  role: implementation
  target: engine/src/StudyStash.App/ViewModels/AiAccessModel.cs
- kind: code
  role: implementation
  target: engine/src/StudyStash.Core/ClaudeAccess.cs
- kind: code
  role: implementation
  target: engine/src/StudyStash.Core/McpClients.cs
- kind: code
  role: implementation
  target: engine/src/StudyStash.Library/LibraryWeb.App.cs
---

# Disconnect AI app

## Trigger

The student no longer wants an AI app to read the library.

## Outcome

Study Stash is taken back out of that app’s settings, or its connection is revoked, and the app no longer reads the library.
