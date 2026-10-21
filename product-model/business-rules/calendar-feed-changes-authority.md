---
appliesTo:
- type: entity
  id: calendar-feed
  effect: changes
references:
- kind: code
  role: implementation
  target: engine/src/StudyStash.Core/Calendar/CalendarSettings.cs
- kind: code
  role: implementation
  target: engine/src/StudyStash.App/ViewModels/CalendarSettingsModel.cs
permits:
- actors:
  - student
---

# Only the student changes which calendars a feed shows

The choice of calendars belongs to the student.
