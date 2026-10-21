---
entities:
- entity: calendar-feed
  shows:
  - Name
  - Address
  - Shown calendars
  - Problem
  collects:
  - Name
  - Address
  - Shown calendars
references:
- kind: code
  role: implementation
  target: engine/src/StudyStash.App/ViewModels/CalendarSettingsModel.cs
- kind: code
  role: implementation
  target: engine/src/StudyStash.Core/Calendar/CalendarKinds.cs
- kind: code
  role: implementation
  target: engine/src/StudyStash.Core/Calendar/CalendarSettings.cs
---

# Calendars

Calendars settings: the calendar feeds the student pasted in, and which of each feed’s calendars are shown.
