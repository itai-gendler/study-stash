---
kind: primary
routes:
  ai-apps: AI apps
steps:
- text: The connected AI app requests the lecture material.
  kind: actor
  actor: ai-agent
  entities:
  - entity: lecture
    effect: reads
    facts: []
  contexts: &id001
    ai-apps:
      place: ai-apps
- text: The Product presents the lecture’s requested content.
  kind: product
  entities:
  - entity: lecture
    effect: reads
    facts:
    - Title
    - Transcript
    - Duration
  contexts: *id001
  actor: ai-agent
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

# Read lecture transcript

## Trigger

The connected AI app requests the lecture material.

## Outcome

The requested material is returned; missing or still-pending material is identified.
