---
appliesTo:
- type: entity
  id: notebook
- type: entity
  id: attachment
references:
- kind: code
  role: implementation
  target: ios/StudyStash/Notebooks/Notebook.swift
- kind: code
  role: implementation
  target: ios/StudyStash/Notebooks/HandwritingView.swift
---

# Deleting a local notebook keeps its saved library copy

The handwritten original and uploaded PDF have independent lifetimes. Saving a changed notebook sends the new PDF before removing its previous uploaded copy.
