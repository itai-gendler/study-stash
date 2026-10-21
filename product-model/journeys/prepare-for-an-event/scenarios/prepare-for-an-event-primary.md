---
kind: primary
result: achieved
routes:
  main: Prepare notes for an upcoming event
steps:
- text: The student opens an event more than a minute before its start.
  kind: actor
  actor: student
  entities: []
  contexts:
    main:
      place: desktop::lecture
  capability: plan-recording
- text: The Product reads the calendar event and opens its planned recording page.
  kind: product
  entities:
  - entity: calendar-event
    effect: reads
    facts:
    - Title
    - Start
    - End
    - All day
    - Location
    - Class match
  - entity: recording
    effect: creates
    facts:
    - Title
    - Class
    - Started
    - Duration
    - Audio
    - Transcript
    - Your notes
    - Timing
    - Calendar event
    - Delivery
    to: Planned
  contexts:
    main:
      place: desktop::lecture
  actor: student
  capability: plan-recording
- text: The student types notes on the upcoming event’s page.
  kind: actor
  actor: student
  entities: []
  contexts:
    main:
      place: desktop::lecture
  capability: take-notes
- text: The Product keeps what the student typed on the planned recording.
  kind: product
  entities:
  - entity: recording
    effect: changes
    facts:
    - Your notes
  contexts:
    main:
      place: desktop::lecture
  actor: student
  capability: take-notes
references:
- kind: code
  role: implementation
  target: engine/src/StudyStash.App/Shell.Recording.cs
- kind: code
  role: implementation
  target: engine/src/StudyStash.App/Services/AppHost.Calendar.cs
- kind: code
  role: implementation
  target: ios/StudyStash/Recording/RecordView.swift
---

# Prepare notes for an upcoming event

## Trigger

The student opens a future event and is taken to its planned lecture page.

## Outcome

Preparation notes are retained on the planned recording.
