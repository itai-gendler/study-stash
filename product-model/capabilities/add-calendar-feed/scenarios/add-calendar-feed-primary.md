---
kind: primary
routes:
  desktop: Desktop app
steps:
- text: The student pastes a calendar’s iCal link in Calendars settings.
  kind: actor
  actor: student
  entities: []
  contexts: &id001
    desktop:
      place: desktop::calendars
- text: The Product reads the feed and saves the calendar feed with its available calendars.
  kind: product
  entities:
  - entity: calendar-feed
    effect: creates
    facts:
    - Name
    - Address
    - Shown calendars
    - Problem
  contexts: *id001
  actor: student
references:
- kind: code
  role: implementation
  target: engine/src/StudyStash.App/ViewModels/CalendarSettingsModel.cs
- kind: code
  role: implementation
  target: engine/src/StudyStash.Core/Calendar/CalendarKinds.cs
---

# Add calendar feed

## Trigger

The student wants upcoming classes from a calendar (Google’s secret iCal address, iCloud, Outlook or the school’s) in Study Stash.

## Outcome

The feed is kept with its calendars, ready for the student to pick which ones to show.

## Edge cases

- An invalid address, duplicate feed or failed feed read leaves the existing source list unchanged.
