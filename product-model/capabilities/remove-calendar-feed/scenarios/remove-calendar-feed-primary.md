---
kind: primary
routes:
  desktop: Desktop app
steps:
- text: The student removes a calendar feed.
  kind: actor
  actor: student
  entities:
  - entity: calendar-feed
    effect: reads
    facts: []
  contexts: &id001
    desktop:
      place: desktop::calendars
- text: The Product removes the calendar feed.
  kind: product
  entities:
  - entity: calendar-feed
    effect: removes
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

# Remove calendar feed

## Trigger

A calendar no longer needs to show in Study Stash.

## Outcome

Its events leave upcoming events, and its calendar choices are forgotten.
