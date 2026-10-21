---
kind: primary
routes:
  desktop: Desktop app
  phone-web-library: Phone web app
  ios-library: iPhone and iPad app
steps:
- text: The student looks at Up next or Coming up.
  kind: actor
  actor: student
  entities: []
  contexts: &id001
    desktop:
      place: desktop::home
    phone-web-library:
      place: phone-web::library::home
    ios-library:
      place: ios::library::home
- text: The Product presents calendar events and their matched class.
  kind: product
  entities:
  - entity: calendar-event
    effect: reads
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
  actor: student
references:
- kind: code
  role: implementation
  target: engine/src/StudyStash.Core/Calendar/Upcoming.cs
- kind: code
  role: implementation
  target: engine/src/StudyStash.Library/LibraryWeb.Calendar.cs
- kind: code
  role: implementation
  target: engine/src/StudyStash.App/ViewModels/ComingUpModel.cs
- kind: code
  role: implementation
  target: web/src/screens/Due.tsx
- kind: code
  role: implementation
  target: ios/StudyStash/Screens/Due/DueViews.swift
---

# Browse upcoming events

## Trigger

The student wants to see which classes and meetings are coming up.

## Outcome

Upcoming events are listed in time order, each with its time and the class it matches.

## Edge cases

- The compact Coming up list excludes all-day and ended events.
