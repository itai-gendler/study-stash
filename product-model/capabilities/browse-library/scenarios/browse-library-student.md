---
kind: primary
routes:
  desktop: Desktop app
  library-web-library: Library web
  phone-web-library: Phone web app
  ios-library: iPhone and iPad app
steps:
- text: The student requests lectures or searches for a topic.
  kind: actor
  actor: student
  entities:
  - entity: lecture
    effect: reads
    facts: []
  contexts: &id001
    desktop:
      place: desktop::home
    library-web-library:
      place: library-web::library::home
    phone-web-library:
      place: phone-web::library::home
    ios-library:
      place: ios::library::home
- text: The Product presents class counts and filed lecture matches, newest first.
  kind: product
  entities:
  - entity: class
    effect: reads
    facts:
    - Name
    - Lecture count
    - Group
  - entity: lecture
    effect: reads
    facts:
    - Title
    - Class
    - Date
    - Topics
    - Filed copy
    - Study notes
    - Transcript
  contexts: *id001
  actor: student
references:
- kind: code
  role: implementation
  target: engine/src/StudyStash.Core/LibraryReader.cs
- kind: code
  role: implementation
  target: engine/src/StudyStash.Core/Store.cs
- kind: code
  role: implementation
  target: engine/src/StudyStash.App/Shell.Overview.cs
- kind: code
  role: implementation
  target: web/src/screens/Home.tsx
- kind: code
  role: implementation
  target: web/src/screens/Search.tsx
- kind: code
  role: implementation
  target: ios/StudyStash/Screens/Library/LibraryTab.swift
- kind: code
  role: implementation
  target: ios/StudyStash/Screens/Search/SearchViews.swift
- kind: code
  role: implementation
  target: engine/src/StudyStash.Core/ClaudeTools.cs
---

# Browse and search the filed library

## Trigger

The student requests lectures or searches for a topic.

## Outcome

Results identify lectures, classes and matching passages; an empty search returns no matches.

## Edge cases

- New lectures still waiting to be filed are absent from the ordinary list; the desktop can show its local pending recordings.
- A previously filed lecture remains available while a replacement is being prepared.
