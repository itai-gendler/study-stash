---
kind: primary
routes:
  ios-library: iPhone and iPad app
steps:
- text: The student chooses Save to library on a notebook.
  kind: actor
  actor: student
  entities:
  - entity: notebook
    effect: reads
    facts: []
  contexts: &id001
    ios-library:
      place: ios::library::notebook
- text: The Product uploads the notebook as an attachment for text extraction.
  kind: product
  entities:
  - entity: notebook
    effect: reads
    facts:
    - Title
    - Pages
    - Destination
    - Changed
    - Saved copy
  - entity: attachment
    effect: creates
    facts:
    - Name
    - Kind
    - Size
    - Added
    - Text
    - Used in notes
    to: Reading
  contexts: *id001
  actor: student
- text: The Product records the notebook’s saved copy.
  kind: product
  entities:
  - entity: notebook
    effect: changes
    facts:
    - Saved copy
  contexts: *id001
  actor: student
references:
- kind: code
  role: implementation
  target: ios/StudyStash/Notebooks/Notebook.swift
- kind: code
  role: implementation
  target: ios/StudyStash/Notebooks/HandwritingView.swift
---

# Save notebook to library

## Trigger

Handwritten notes should go with their class or lecture in the library.

## Outcome

A PDF of the pages is attached to the class or lecture, and its handwriting is read on the library’s computer.

## Edge cases

- A later save uploads the new copy before trying to remove the previous attachment.
- If upload fails, the original notebook remains on the device and still needs saving.
