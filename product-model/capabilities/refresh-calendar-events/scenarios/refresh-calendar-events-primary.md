---
kind: primary
routes:
  desktop: Desktop app
  phone-web-library: Phone web app
  ios-library: iPhone and iPad app
steps:
- text: The capture computer refreshes its selected calendars.
  kind: condition
  unattended: true
  entities: []
  contexts: &id001
    desktop:
      place: desktop::home
    phone-web-library:
      place: phone-web::library::home
    ios-library:
      place: ios::library::home
- text: The Product refreshes calendar event details and class matches.
  kind: product
  entities:
  - entity: calendar-event
    effect: creates
    facts:
    - Title
    - Start
    - End
    - All day
    - Location
    - Class match
  - entity: class
    effect: reads
    facts: []
  contexts: *id001
references:
- kind: code
  role: implementation
  target: engine/src/StudyStash.Core/Calendar/Upcoming.cs
- kind: code
  role: implementation
  target: engine/src/StudyStash.Core/Calendar/UpcomingSender.cs
- kind: code
  role: implementation
  target: engine/src/StudyStash.Core/Calendar/LibraryCalendar.cs
---

# Refresh calendar events

## Trigger

The recording computer refreshes its selected calendars.

## Outcome

The merged schedule is available in time order, with cancelled and duplicate occurrences omitted.

## Edge cases

- A source that fails keeps its previous events and reports its problem.
- The read covers the current week and seven days ahead.
- A library-only desktop does not collect calendars itself.
