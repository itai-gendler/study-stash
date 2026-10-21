---
appliesTo:
- type: entity
  id: notebook
  effect: changes
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

# Only the student writes in a notebook

Pages, title and destination change only as the student writes and saves.
