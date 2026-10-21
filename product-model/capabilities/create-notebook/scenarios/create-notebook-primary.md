---
kind: primary
routes:
  ios-library: iPhone and iPad app
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
    ios-library:
      place: ios::library::notebook
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
    ios-library:
      place: ios::library::notebook
  actor: student
references:
- kind: code
  role: implementation
  target: ios/StudyStash/Notebooks/Notebook.swift
- kind: code
  role: implementation
  target: ios/StudyStash/Notebooks/HandwritingView.swift
---

# Create notebook

## Trigger

The student wants to write notes by hand on iPhone or iPad.

## Outcome

The notebook opens, ready to write in.

## Edge cases

- Opening handwriting for a lecture with an existing notebook reopens that notebook.
