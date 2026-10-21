---
kind: primary
routes:
  ios-library: iPhone and iPad app
steps:
- text: The student writes on a notebook’s pages, adds or removes pages, or renames it.
  kind: actor
  actor: student
  entities:
  - entity: notebook
    effect: reads
    facts: []
  contexts: &id001
    ios-library:
      place: ios::library::notebook
- text: The Product saves the notebook pages, title and editing time locally.
  kind: product
  entities:
  - entity: notebook
    effect: changes
    facts:
    - Pages
    - Title
    - Changed
  contexts: *id001
  actor: student
references:
- kind: code
  role: implementation
  target: ios/StudyStash/Notebooks/HandwritingView.swift
- kind: code
  role: implementation
  target: ios/StudyStash/Notebooks/Notebook.swift
---

# Edit notebook

## Trigger

The student is taking or tidying handwritten notes.

## Outcome

The pages and title are kept on the device as they are written.
