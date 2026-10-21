---
kind: primary
routes:
  library-web-library: Library web
steps:
- text: The student picks the engine for writing notes, for Ask, for sorting into classes and for drawing rich notes in the library’s web Settings.
  kind: actor
  actor: student
  entities:
  - entity: ai-settings
    effect: reads
    facts: []
  contexts:
    library-web-library: &id001
      place: library-web::library::your-ai
- text: The Product saves Your AI engine choices.
  kind: product
  entities:
  - entity: ai-settings
    effect: changes
    facts:
    - Notes engine
    - Ask engine
    - Sorting engine
    - Rich notes
  contexts:
    library-web-library: *id001
  actor: student
references:
- kind: code
  role: implementation
  target: engine/src/StudyStash.Library/LibraryWeb.cs
---

# Choose AI jobs in web Settings

## Trigger

The student saves the AI choices in browser Settings.

## Outcome

Notes, sorting, question answering and rich-note generation use the selected provider choices.
