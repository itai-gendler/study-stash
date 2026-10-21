---
kind: primary
routes:
  ai-apps: AI apps
steps:
- text: The connected AI app requests lectures or searches for a topic.
  kind: actor
  actor: ai-agent
  entities:
  - entity: lecture
    effect: reads
    facts: []
  contexts: &id001
    ai-apps:
      place: ai-apps
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
    - Search passages
  contexts: *id001
  actor: ai-agent
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

The connected AI app requests lectures or searches for a topic.

## Outcome

Results identify lectures, classes and matching passages; an empty search returns no matches.

## Edge cases

- New lectures still waiting to be filed are absent from the ordinary list; the desktop can show its local pending recordings.
- A previously filed lecture remains available while a replacement is being prepared.
