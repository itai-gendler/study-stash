---
singleton: true
references:
- kind: code
  role: implementation
  target: engine/src/StudyStash.Core/Ai/AiSettings.cs
- kind: code
  role: implementation
  target: engine/src/StudyStash.Core/Ai/ToolAccess.cs
- kind: code
  role: implementation
  target: engine/src/StudyStash.Core/Ai/Engines.cs
- kind: code
  role: implementation
  target: engine/src/StudyStash.App/ViewModels/AiAccessModel.cs
---

# Your AI

Which engines do the library’s work and the student’s reading choices for connected AI apps.

## Information kept

- **Notes engine** — The model used for the write-up.
- **Ask engine** — The default model for questions.
- **Sorting engine** — The model used for automatic filing.
- **Chat engine** — The model used for saved conversations.
- **Fallback** — Whether Ollama may answer when another provider cannot.
- **Rich notes** — Whether diagrams, formula plots and drawings are requested.
- **Reading enabled** — Whether AI apps may read the library.
- **Lectures and transcripts** — Whether AI apps may list, search and read lectures and their transcripts.
- **Study notes** — Whether AI apps may read study notes and attachments.
- **Canvas assignments and files** — Whether AI apps may read Canvas work and the library’s files.
- **Web access** — Whether remote AI apps may connect.
- **Engine readiness** — Installation, sign-in, usage limits and latest test results.
