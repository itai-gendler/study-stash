---
kind: primary
routes:
  desktop: Desktop app
steps:
- text: The student chooses Markdown or PDF for a lecture, or downloads a class.
  kind: actor
  actor: student
  entities:
  - entity: class
    effect: reads
    facts: []
  - entity: lecture
    effect: reads
    facts: []
  contexts: &id001
    desktop:
      place: desktop::lecture
- text: The Product exports the lecture notes and selected transcript content.
  kind: product
  entities:
  - entity: lecture
    effect: reads
    facts:
    - Title
    - Study notes
    - Transcript
    - Date
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

# Download a lecture or class

## Trigger

The student chooses Markdown or PDF for a lecture, or downloads a class.

## Outcome

The selected notes are saved, with the requested transcript and diagrams when supported.

## Edge cases

- Cancelling the file selection changes nothing.
- A PDF generation failure leaves the chosen file unchanged.
