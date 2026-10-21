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
domain: calendars
---

# Browse upcoming events

See upcoming classes and meetings, including their time and matching class.
