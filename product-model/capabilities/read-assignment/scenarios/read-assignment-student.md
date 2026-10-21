---
kind: primary
routes:
  desktop: Desktop app
  library-web-library: Library web
  phone-web-library: Phone web app
  ios-library: iPhone and iPad app
steps:
- text: The student opens an assignment.
  kind: actor
  actor: student
  entities:
  - entity: assignment
    effect: reads
    facts: []
  contexts: &id001
    desktop:
      place: desktop::assignment
    library-web-library:
      place: library-web::library::assignment
    phone-web-library:
      place: phone-web::library::assignment
    ios-library:
      place: ios::library::assignment
- text: The Product presents the assignment details.
  kind: product
  entities:
  - entity: assignment
    effect: reads
    facts:
    - Title
    - Due
    - Status
    - Instructions
    - Rubric
    - Submission
    - Feedback
    - Link
  contexts: *id001
  actor: student
references:
- kind: code
  role: implementation
  target: engine/src/StudyStash.Library/LibraryWeb.Canvas.cs
- kind: code
  role: implementation
  target: engine/src/StudyStash.App/ViewModels/AssignmentModel.cs
- kind: code
  role: implementation
  target: web/src/screens/Assignment.tsx
- kind: code
  role: implementation
  target: ios/StudyStash/Screens/Due/DueViews.swift
- kind: code
  role: implementation
  target: engine/src/StudyStash.Core/ClaudeTools.cs
---

# Read assignment details

## Trigger

The student opens an assignment.

## Outcome

The available instructions and personal submission context are shown, with a link back to Canvas.
