---
kind: primary
routes:
  ios-library: iPhone and iPad app
steps:
- text: The student deletes a notebook on the iPhone or iPad.
  kind: actor
  actor: student
  entities:
  - entity: notebook
    effect: reads
    facts: []
  contexts: &id001
    ios-library:
      place: ios::library::notebook
- text: The Product removes the notebook from this device.
  kind: product
  entities:
  - entity: notebook
    effect: removes
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

# Delete notebook

## Trigger

A handwritten notebook is no longer needed on the device.

## Outcome

The notebook leaves the device; a copy already saved to the library stays there.
