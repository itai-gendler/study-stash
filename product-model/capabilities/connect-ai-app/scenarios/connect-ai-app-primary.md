---
kind: primary
routes:
  desktop: Desktop app
steps:
- text: The student chooses Connect next to an AI app on this computer.
  kind: actor
  actor: student
  entities: []
  contexts: &id001
    desktop:
      place: desktop::ai-apps
- text: The Product adds an AI app connection and reports whether the app has loaded it.
  kind: product
  entities:
  - entity: ai-connection
    effect: creates
    facts:
    - Name
    - Kind
    - Status
    - Last used
  contexts: *id001
  actor: student
- text: The Product keeps the student’s AI connection choice.
  kind: product
  entities:
  - entity: student
    effect: changes
    facts:
    - AI connection
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

# Connect AI app

## Trigger

The student wants an AI app on this computer to read their library.

## Outcome

Study Stash is added to that app’s own settings, and the row shows Connected once the app has been reopened and loads it.

## Edge cases

- Local apps may need to quit and reopen or start a new session before the connection becomes active.
- A remote app follows the library’s sign-in and consent process.
