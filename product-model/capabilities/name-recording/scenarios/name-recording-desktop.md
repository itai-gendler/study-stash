---
kind: primary
routes:
  desktop: Desktop app
steps:
- text: The student edits the recording title.
  kind: actor
  actor: student
  entities:
  - entity: recording
    effect: reads
    facts: []
  contexts: &id001
    desktop:
      place: desktop::recording
- text: The Product records the title as the student’s choice.
  kind: product
  entities:
  - entity: recording
    effect: changes
    facts:
    - Title
  contexts: *id001
  actor: student
references:
- kind: code
  role: implementation
  target: engine/src/StudyStash.App/Services/AppHost.cs
- kind: code
  role: implementation
  target: engine/src/StudyStash.App/Shell.Recording.cs
- kind: code
  role: implementation
  target: ios/StudyStash/Recording/RecordView.swift
---

# Name on the computer

## Trigger

The student edits the recording title.

## Outcome

The typed title is retained for filing.
