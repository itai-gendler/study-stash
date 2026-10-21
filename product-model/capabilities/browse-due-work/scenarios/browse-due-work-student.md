---
kind: primary
routes:
  desktop: Desktop app
  library-web-library: Library web
  phone-web-library: Phone web app
  ios-library: iPhone and iPad app
steps:
- text: The student opens Due.
  kind: actor
  actor: student
  entities: []
  contexts: &id001
    desktop:
      place: desktop::due
    library-web-library:
      place: library-web::library::due
    phone-web-library:
      place: phone-web::library::due
    ios-library:
      place: ios::library::due
- text: The Product presents assignment titles, dates and statuses.
  kind: product
  entities:
  - entity: assignment
    effect: reads
    facts:
    - Title
    - Due
    - Status
    - Link
  contexts: *id001
  actor: student
references:
- kind: code
  role: implementation
  target: engine/src/StudyStash.Core/Canvas/Assignments.cs
- kind: code
  role: implementation
  target: engine/src/StudyStash.Library/LibraryWeb.Canvas.cs
- kind: code
  role: implementation
  target: engine/src/StudyStash.App/ViewModels/DueCalendarModel.cs
- kind: code
  role: implementation
  target: web/src/screens/Due.tsx
- kind: code
  role: implementation
  target: ios/StudyStash/Screens/Due/DueViews.swift
- kind: code
  role: implementation
  target: engine/src/StudyStash.Core/ClaudeTools.cs
---

# Read due work

## Trigger

The student opens Due.

## Outcome

Due work is ordered and grouped with its current Canvas status; work without a date is still represented.
