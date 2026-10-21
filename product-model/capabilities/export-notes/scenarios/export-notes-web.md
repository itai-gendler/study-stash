---
kind: primary
routes:
  library-web-library: Library web
steps:
- text: The student downloads a note or the class archive.
  kind: actor
  actor: student
  entities:
  - entity: class
    effect: reads
    facts: []
  contexts: &id001
    library-web-library:
      place: library-web::library::lecture
- text: The Product exports filed lecture content.
  kind: product
  entities:
  - entity: lecture
    effect: reads
    facts:
    - Title
    - Study notes
    - Transcript
    - Class
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

# Download from the web library

## Trigger

The student downloads a note or the class archive.

## Outcome

A Markdown note or class ZIP is returned.
