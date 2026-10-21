---
kind: primary
routes:
  desktop: Desktop app
steps:
- text: The student chooses Set it up for the free AI on this computer, Claude or ChatGPT.
  kind: actor
  actor: student
  entities: []
  contexts: &id001
    desktop:
      place: desktop::your-ai
- text: The Product checks the selected engine and records Your AI readiness.
  kind: product
  entities:
  - entity: ai-settings
    effect: changes
    facts:
    - Engine readiness
  contexts: *id001
  actor: student
references:
- kind: code
  role: implementation
  target: engine/src/StudyStash.App/ViewModels/AiEnginesModel.cs
- kind: code
  role: implementation
  target: engine/src/StudyStash.Core/Ai/Engines.cs
- kind: code
  role: implementation
  target: engine/src/StudyStash.Library/LibraryWeb.Ai.cs
---

# Set up AI engine

## Trigger

The student wants an AI to write their notes and answer their questions.

## Outcome

The engine is installed and signed in on its maker’s own page, and a short test checks that the student’s plan includes it.

## Edge cases

- A provider needing sign-in or a paid plan explains that requirement.
- Installation and authentication need explicit user action in the setup controls.
- A failed readiness test leaves the existing engine choices available to change.
