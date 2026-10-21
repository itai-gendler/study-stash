---
relations:
- entity: calendar-event
  verb: supplies
  cardinality: one-to-many
references:
- kind: code
  role: implementation
  target: engine/src/StudyStash.Core/Calendar/CalendarSettings.cs
- kind: code
  role: implementation
  target: engine/src/StudyStash.App/ViewModels/CalendarSettingsModel.cs
---

# Calendar feed

An iCalendar source the student added on a recording computer.

## Information kept

- **Name** — The source’s displayed name.
- **Address** — The feed address supplied by the student.
- **Shown calendars** — The calendars whose events are included.
- **Problem** — The latest reading problem, if any.
