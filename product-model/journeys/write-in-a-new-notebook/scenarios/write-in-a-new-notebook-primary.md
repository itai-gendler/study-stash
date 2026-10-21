---
kind: primary
result: achieved
routes:
  main: Write in a new notebook
steps:
- text: The student starts a notebook for a class or a lecture, blank or from a PDF or notebook export.
  kind: actor
  actor: student
  entities:
  - entity: class
    effect: reads
    facts: []
  - entity: lecture
    effect: reads
    facts: []
  - entity: notebook
    effect: reads
    facts: []
  contexts:
    main:
      place: ios::library::notebook
  capability: create-notebook
- text: The Product creates the notebook and opens its page for writing.
  kind: product
  entities:
  - entity: notebook
    effect: creates
    facts:
    - Title
    - Pages
    - Destination
    - Changed
    - Saved copy
  contexts:
    main:
      place: ios::library::notebook
  actor: student
  capability: create-notebook
- text: The student writes on the new notebook’s first page.
  kind: actor
  actor: student
  entities:
  - entity: notebook
    effect: reads
    facts: []
  contexts:
    main:
      place: ios::library::notebook
  capability: edit-notebook
- text: The Product saves the notebook pages, title and editing time locally.
  kind: product
  entities:
  - entity: notebook
    effect: changes
    facts:
    - Pages
    - Title
    - Changed
  contexts:
    main:
      place: ios::library::notebook
  actor: student
  capability: edit-notebook
references:
- kind: code
  role: implementation
  target: ios/StudyStash/Notebooks/Notebook.swift
- kind: code
  role: implementation
  target: ios/StudyStash/Notebooks/HandwritingView.swift
---

# Write in a new notebook

## Trigger

The student starts handwritten notes and is taken into the new notebook.

## Outcome

The notebook keeps the student’s ink locally.
