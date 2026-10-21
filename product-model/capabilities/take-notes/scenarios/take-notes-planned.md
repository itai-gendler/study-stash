---
kind: primary
routes:
  desktop: Desktop app
steps:
- text: The student types notes on the upcoming event’s page.
  kind: actor
  actor: student
  entities: []
  contexts: &id001
    desktop:
      place: desktop::lecture
- text: The Product keeps what the student typed on the planned recording.
  kind: product
  entities:
  - entity: recording
    effect: changes
    facts:
    - Your notes
  contexts: *id001
  actor: student
references:
- kind: code
  role: implementation
  target: engine/src/StudyStash.App/Shell.Recording.cs
- kind: code
  role: implementation
  target: ios/StudyStash/Recording/RecordView.swift
---

# Write before the event

## Trigger

The student types notes on an upcoming lecture’s page before it starts.

## Outcome

The planned recording retains the notes; this makes it eligible to start when the event begins.
