---
entities:
- entity: ai-settings
  shows:
  - Notes engine
  - Ask engine
  - Sorting engine
  - Chat engine
  - Fallback
  - Rich notes
  - Engine readiness
  collects:
  - Notes engine
  - Ask engine
  - Sorting engine
  - Chat engine
  - Fallback
  - Rich notes
references:
- kind: code
  role: implementation
  target: engine/src/StudyStash.App/ViewModels/AiEnginesModel.cs
- kind: code
  role: implementation
  target: engine/src/StudyStash.Core/Ai/AiSettings.cs
- kind: code
  role: implementation
  target: engine/src/StudyStash.Core/Ai/Engines.cs
- kind: code
  role: implementation
  target: engine/src/StudyStash.Library/LibraryWeb.Ai.cs
---

# Your AI

Your AI settings: who writes the notes, answers questions, sorts lectures and draws rich notes, whether Ollama stands in, and each engine’s set-up state.
