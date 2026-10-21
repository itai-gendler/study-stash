---
references:
- kind: code
  role: implementation
  target: engine/src/StudyStash.Core/Calendar/Upcoming.cs
- kind: code
  role: implementation
  target: engine/src/StudyStash.Core/Calendar/RecordedEvent.cs
---

# Calendar event

An upcoming class or meeting read from a selected calendar.

## Information kept

- **Title** — The event name.
- **Start** — When it begins.
- **End** — When it ends.
- **All day** — Whether the event lasts all day.
- **Location** — The place or meeting link.
- **Class match** — The class matched from its name, aliases or Canvas code.
