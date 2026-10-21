---
appliesTo:
- type: entity
  id: notebook
  effect: removes
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

# Only the student deletes a notebook

Deleting a notebook removes it from the device.
