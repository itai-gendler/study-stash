---
kind: primary
routes:
  desktop: Desktop app
  library-web-library: Library web
  phone-web-library: Phone web app
  ios-library: iPhone and iPad app
steps:
- text: The student opens the lecture.
  kind: actor
  actor: student
  entities:
  - entity: lecture
    effect: reads
    facts: []
  contexts: &id001
    desktop:
      place: desktop::lecture
    library-web-library:
      place: library-web::library::lecture
    phone-web-library:
      place: phone-web::library::lecture
    ios-library:
      place: ios::library::lecture
- text: The Product presents the lecture’s requested content.
  kind: product
  entities:
  - entity: lecture
    effect: reads
    facts:
    - Title
    - Class
    - Date
    - Study notes
    - Your notes
    - Writer
    - Problem
  contexts: *id001
  actor: student
references:
- kind: code
  role: implementation
  target: engine/src/StudyStash.Core/LibraryReader.cs
- kind: code
  role: implementation
  target: engine/src/StudyStash.Core/ClaudeTools.cs
- kind: code
  role: implementation
  target: engine/src/StudyStash.App/Shell.Library.cs
- kind: code
  role: implementation
  target: web/src/screens/LectureScreen.tsx
- kind: code
  role: implementation
  target: ios/StudyStash/Screens/Library/LectureView.swift
---

# Read lecture notes

## Trigger

The student opens the lecture.

## Outcome

The requested material is returned; missing or still-pending material is identified.
