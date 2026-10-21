---
appliesTo:
- type: entity
  id: calendar-event
  effect: creates
references:
- kind: code
  role: implementation
  target: engine/src/StudyStash.Core/Calendar/Upcoming.cs
- kind: code
  role: implementation
  target: engine/src/StudyStash.Core/Calendar/RecordedEvent.cs
permits:
- unattended: true
---

# Calendar events come only from refreshing the student’s calendars

Events are read from the calendar feeds the student added; Study Stash never adds an event of its own.
