---
availability:
- place: desktop
- place: phone-web::library
- place: ios::library
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
domain: calendars
---

# Refresh calendar events

Read selected calendars, merge their events and make the upcoming schedule available to the library.
