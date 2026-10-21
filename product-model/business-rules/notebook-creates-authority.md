---
appliesTo:
- type: entity
  id: notebook
  effect: creates
references:
- kind: code
  role: implementation
  target: ios/StudyStash/Notebooks/Notebook.swift
- kind: code
  role: implementation
  target: ios/StudyStash/Notebooks/HandwritingView.swift
permits:
- actors:
  - student
---

# Only the student creates a notebook

Notebooks are the student’s handwriting on iPhone or iPad.
