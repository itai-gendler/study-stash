---
kind: primary
routes:
  desktop: Desktop app
steps:
- text: The student picks which of a feed’s calendars to show.
  kind: actor
  actor: student
  entities: []
  contexts: &id001
    desktop:
      place: desktop::calendars
- text: The Product keeps the calendar feed’s shown-calendar selection and refreshes upcoming events.
  kind: product
  entities:
  - entity: calendar-feed
    effect: changes
    facts:
    - Shown calendars
  contexts: *id001
  actor: student
references:
- kind: code
  role: implementation
  target: engine/src/StudyStash.App/ViewModels/CalendarSettingsModel.cs
- kind: code
  role: implementation
  target: engine/src/StudyStash.Core/Calendar/CalendarSettings.cs
---

# Change calendar settings

## Trigger

A connected feed holds calendars the student does or does not want in upcoming events.

## Outcome

Only the chosen calendars’ events appear in upcoming events.
