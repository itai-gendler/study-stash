---
references:
- kind: code
  role: implementation
  target: engine/src/StudyStash.Core/Canvas/CanvasIndex.cs
- kind: code
  role: implementation
  target: engine/src/StudyStash.App/ViewModels/CanvasReaderModel.cs
- kind: code
  role: implementation
  target: engine/src/StudyStash.App/ViewModels/CanvasClassModel.cs
---

# Announcement

A Canvas announcement mirrored into its class, with a locally kept read indication.

## Information kept

- **Title** — The announcement heading.
- **Body** — The full announcement text.
- **Author** — Who posted it.
- **Posted** — When it was published.
- **Source** — Its Canvas address.
- **New** — Whether it has not yet been read in Study Stash.
