---
kind: primary
routes:
  desktop: Desktop app
steps:
- text: A planned event has begun, has not ended, has typed notes and no other capture is active.
  kind: condition
  unattended: true
  entities: []
  contexts: &id001
    desktop:
      place: desktop::lecture
- text: The Product starts the planned recording.
  kind: product
  entities:
  - entity: recording
    effect: changes
    facts:
    - Audio
    - Duration
    from: Planned
    to: Recording
  contexts: *id001
references:
- kind: code
  role: implementation
  target: engine/src/StudyStash.App/Services/AppHost.Calendar.cs
- kind: code
  role: implementation
  target: engine/src/StudyStash.App/Shell.Recording.cs
---

# Start a prepared event

## Trigger

A planned event has begun, has not ended, has typed notes and no other capture is active.

## Outcome

The prepared recording starts with its existing notes.
