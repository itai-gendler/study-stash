---
appliesTo:
- type: entity
  id: calendar-event
- type: entity
  id: calendar-feed
references:
- kind: code
  role: implementation
  target: engine/src/StudyStash.Core/Calendar/CalendarKinds.cs
- kind: code
  role: implementation
  target: engine/src/StudyStash.Core/Calendar/Upcoming.cs
---

# Calendar events are read from their source

Study Stash keeps a selected, refreshed schedule for recording and study. Editing the original event takes place in its calendar service.
