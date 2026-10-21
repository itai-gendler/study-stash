---
availability:
- place: desktop
- place: library-web::library
- place: phone-web::library
- place: ios::library
- place: ai-apps
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
domain: due
---

# Read assignment

Read an assignment’s instructions, rubric, the student’s submission and the grader’s feedback.
