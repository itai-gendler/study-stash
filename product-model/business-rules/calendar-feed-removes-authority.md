---
appliesTo:
- type: entity
  id: calendar-feed
  effect: removes
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

# Only the student removes a calendar feed

Removing a feed forgets its calendar choices.
