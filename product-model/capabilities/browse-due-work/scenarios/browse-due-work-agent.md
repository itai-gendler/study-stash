---
kind: primary
routes:
  ai-apps: AI apps
steps:
- text: The connected AI app asks what is due.
  kind: actor
  actor: ai-agent
  entities: []
  contexts: &id001
    ai-apps:
      place: ai-apps
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
  actor: ai-agent
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

The connected AI app asks what is due.

## Outcome

Due work is ordered and grouped with its current Canvas status; work without a date is still represented.
