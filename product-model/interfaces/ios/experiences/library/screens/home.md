---
entities:
- entity: calendar-event
  shows:
  - Title
  - Start
  - End
  - All day
  - Location
  - Class match
- entity: class
  shows:
  - Name
  - Group
  - Lecture count
- entity: lecture
  shows:
  - Title
  - Class
  - Date
  - Transcript
  - Study notes
  - Topics
  - Filed copy
references:
- kind: code
  role: implementation
  target: engine/src/StudyStash.App/Shell.Overview.cs
- kind: code
  role: implementation
  target: engine/src/StudyStash.App/ViewModels/ComingUpModel.cs
- kind: code
  role: implementation
  target: engine/src/StudyStash.Core/Calendar/LibraryCalendar.cs
- kind: code
  role: implementation
  target: engine/src/StudyStash.Core/Calendar/Upcoming.cs
- kind: code
  role: implementation
  target: engine/src/StudyStash.Core/Calendar/UpcomingSender.cs
- kind: code
  role: implementation
  target: engine/src/StudyStash.Core/ClaudeTools.cs
- kind: code
  role: implementation
  target: engine/src/StudyStash.Core/LibraryReader.cs
- kind: code
  role: implementation
  target: engine/src/StudyStash.Core/Store.cs
- kind: code
  role: implementation
  target: engine/src/StudyStash.Library/LibraryWeb.Calendar.cs
- kind: code
  role: implementation
  target: ios/StudyStash/App/AppModel.swift
- kind: code
  role: implementation
  target: ios/StudyStash/Screens/Due/DueViews.swift
- kind: code
  role: implementation
  target: ios/StudyStash/Screens/Library/LibraryTab.swift
- kind: code
  role: implementation
  target: ios/StudyStash/Screens/Search/SearchViews.swift
- kind: code
  role: implementation
  target: web/src/data/resource.ts
- kind: code
  role: implementation
  target: web/src/screens/Due.tsx
- kind: code
  role: implementation
  target: web/src/screens/Home.tsx
- kind: code
  role: implementation
  target: web/src/screens/Search.tsx
---

# Library

The library on iPhone and iPad: what is coming up, the classes and the filed lectures, with search.
