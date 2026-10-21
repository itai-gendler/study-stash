---
entities:
- entity: ai-settings
  shows:
  - Notes engine
  - Ask engine
  - Sorting engine
  - Rich notes
  collects:
  - Notes engine
  - Ask engine
  - Sorting engine
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
  target: engine/src/StudyStash.Library/LibraryWeb.Ai.cs
---

# Your AI

Your AI in the library’s web Settings: who writes the notes, answers questions, sorts lectures and draws rich notes.
