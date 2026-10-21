---
kind: primary
routes:
  desktop: Desktop app
steps:
- text: The student switches on or off what AI apps may read, and whether they may connect from the web.
  kind: actor
  actor: student
  entities: []
  contexts: &id001
    desktop:
      place: desktop::ai-apps
- text: The Product saves Your AI reading choices for subsequent tool calls.
  kind: product
  entities:
  - entity: ai-settings
    effect: changes
    facts:
    - Reading enabled
    - Lectures and transcripts
    - Study notes
    - Canvas assignments and files
    - Web access
  contexts: *id001
  actor: student
references:
- kind: code
  role: implementation
  target: engine/src/StudyStash.App/ViewModels/AiAccessModel.cs
- kind: code
  role: implementation
  target: engine/src/StudyStash.Core/Ai/ToolAccess.cs
- kind: code
  role: implementation
  target: engine/src/StudyStash.Library/LibraryWeb.App.cs
---

# Change AI apps settings

## Trigger

The student wants to decide what their AI apps may read, and from where.

## Outcome

The next call from any connected AI app follows the new choices.

## Edge cases

- Changing reading choices applies to the next call without requiring apps to reconnect.
