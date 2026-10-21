---
entities:
- entity: notebook
  shows:
  - Title
  - Pages
  - Destination
  - Changed
  - Saved copy
  collects:
  - Title
  - Pages
- entity: attachment
  shows:
  - Name
  - Kind
  - Size
  - Added
  - Text
  - Used in notes
- entity: class
  shows:
  - Name
- entity: lecture
  shows:
  - Title
references:
- kind: code
  role: implementation
  target: ios/StudyStash/Notebooks/HandwritingView.swift
- kind: code
  role: implementation
  target: ios/StudyStash/Notebooks/Notebook.swift
---

# Notebook

A handwritten notebook: its pages, the class or lecture it belongs to, and Save to library.
