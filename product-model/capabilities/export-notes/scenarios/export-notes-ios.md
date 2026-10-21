---
kind: primary
routes:
  ios-library: iPhone and iPad app
steps:
- text: The student chooses Share in the native lecture view.
  kind: actor
  actor: student
  entities:
  - entity: lecture
    effect: reads
    facts: []
  contexts: &id001
    ios-library:
      place: ios::library::lecture
- text: The Product prepares the lecture text for sharing.
  kind: product
  entities:
  - entity: lecture
    effect: reads
    facts:
    - Title
    - Study notes
  contexts: *id001
  actor: student
references:
- kind: code
  role: implementation
  target: engine/src/StudyStash.App/Services/NotesDownload.cs
- kind: code
  role: implementation
  target: engine/src/StudyStash.Library/LibraryWeb.cs
- kind: code
  role: implementation
  target: ios/StudyStash/Screens/Library/LectureView.swift
---

# Share native lecture text

## Trigger

The student chooses Share in the native lecture view.

## Outcome

The system share flow receives the lecture’s title and notes.
