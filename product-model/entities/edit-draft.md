---
references:
- kind: code
  role: implementation
  target: engine/src/StudyStash.App/Services/NoteDrafts.cs
- kind: code
  role: implementation
  target: engine/src/StudyStash.App/ViewModels/AiNotesModel.cs
---

# Edit draft

Typing in a desktop notes editor that has not been saved to the library.

## Information kept

- **Text** — The unsaved editor text.
- **Original notes** — The version the edit started from.
- **Kept at** — When the typing was saved locally for recovery.
