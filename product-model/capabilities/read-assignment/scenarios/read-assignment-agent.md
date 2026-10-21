---
kind: primary
routes:
  ai-apps: AI apps
steps:
- text: The connected AI app requests an assignment.
  kind: actor
  actor: ai-agent
  entities:
  - entity: assignment
    effect: reads
    facts: []
  contexts: &id001
    ai-apps:
      place: ai-apps
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
  actor: ai-agent
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

The connected AI app requests an assignment.

## Outcome

The available instructions and personal submission context are shown, with a link back to Canvas.
