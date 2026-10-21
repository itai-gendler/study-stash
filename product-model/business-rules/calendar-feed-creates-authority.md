---
appliesTo:
- type: entity
  id: calendar-feed
  effect: creates
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

# Only the student adds a calendar feed

A feed is the iCal link the student pasted in.
