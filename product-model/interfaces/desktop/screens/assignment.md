---
entities:
- entity: assignment
  shows:
  - Title
  - Due
  - Status
  - Instructions
  - Rubric
  - Submission
  - Feedback
  - Link
references:
- kind: code
  role: implementation
  target: engine/src/StudyStash.App/ViewModels/AssignmentModel.cs
- kind: code
  role: implementation
  target: engine/src/StudyStash.Core/ClaudeTools.cs
- kind: code
  role: implementation
  target: engine/src/StudyStash.Library/LibraryWeb.Canvas.cs
- kind: code
  role: implementation
  target: ios/StudyStash/Screens/Due/DueViews.swift
- kind: code
  role: implementation
  target: web/src/screens/Assignment.tsx
---

# Assignment

One Canvas assignment as Study Stash mirrors it: instructions, rubric, the student’s submission and the grader’s feedback, with a link back to Canvas.
