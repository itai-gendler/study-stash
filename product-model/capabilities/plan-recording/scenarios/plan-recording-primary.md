---
kind: primary
routes:
  desktop: Desktop app
steps:
- text: The student opens an event more than a minute before its start.
  kind: actor
  actor: student
  entities: []
  contexts: &id001
    desktop:
      place: desktop::lecture
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
  contexts: *id001
  actor: student
references:
- kind: code
  role: implementation
  target: engine/src/StudyStash.App/Shell.Recording.cs
- kind: code
  role: implementation
  target: engine/src/StudyStash.App/Services/AppHost.Calendar.cs
---

# Prepare an upcoming recording

## Trigger

The student opens an event more than a minute before its start.

## Outcome

The planned recording page is ready for the student’s own notes.

## Edge cases

- An event that starts within a minute, or is already on, records at once instead of opening a planned page.
- A planned page left empty is not kept once the student leaves it.
- Typing anything on the page makes it record on its own when the event starts, unless another recording is running.
