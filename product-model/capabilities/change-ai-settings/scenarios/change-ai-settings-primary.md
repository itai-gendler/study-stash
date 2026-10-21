---
kind: primary
routes:
  desktop: Desktop app
steps:
- text: The student picks the engine for writing notes, for Ask, for sorting into classes and for drawing rich notes.
  kind: actor
  actor: student
  entities:
  - entity: ai-settings
    effect: reads
    facts: []
  contexts:
    desktop: &id001
      place: desktop::your-ai
- text: The Product saves Your AI engine choices.
  kind: product
  entities:
  - entity: ai-settings
    effect: changes
    facts:
    - Notes engine
    - Ask engine
    - Chat engine
    - Sorting engine
    - Fallback
    - Rich notes
  contexts:
    desktop: *id001
  actor: student
references:
- kind: code
  role: implementation
  target: engine/src/StudyStash.App/ViewModels/AiEnginesModel.cs
- kind: code
  role: implementation
  target: engine/src/StudyStash.Core/Ai/AiSettings.cs
- kind: code
  role: implementation
  target: engine/src/StudyStash.Library/LibraryWeb.Ai.cs
---

# Change Your AI settings

## Trigger

The student wants a different engine, or a different one for each job.

## Outcome

New notes, answers, sorting and rich notes use the chosen engines, with Ollama standing in when that fallback is on.
