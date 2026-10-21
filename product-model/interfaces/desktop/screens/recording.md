---
entities:
- entity: recording
  shows:
  - Title
  - Class
  - Started
  - Duration
  - Audio
  - Transcript
  - Your notes
  - Timing
  - Calendar event
  - Delivery
  collects:
  - Title
  - Your notes
- entity: class
  shows:
  - Name
references:
- kind: code
  role: implementation
  target: engine/src/StudyStash.App/Services/AppHost.cs
- kind: code
  role: implementation
  target: engine/src/StudyStash.App/Shell.Recording.cs
- kind: code
  role: implementation
  target: engine/src/StudyStash.Core/Recording/Lectures.cs
- kind: code
  role: implementation
  target: engine/src/StudyStash.Core/Recording/Recorder.cs
- kind: code
  role: implementation
  target: engine/src/StudyStash.Library/LibraryWeb.PhoneLectures.cs
- kind: code
  role: implementation
  target: ios/StudyStash/Recording/RecordView.swift
- kind: code
  role: implementation
  target: ios/StudyStash/Recording/Recorder.swift
- kind: code
  role: implementation
  target: ios/StudyStash/Recording/Recording.swift
- kind: code
  role: implementation
  target: ios/StudyStash/Screens/Library/LibraryTab.swift
---

# Recording

The page of a lecture being recorded: how long it has run, Pause and Stop, the words heard so far, and the student’s own notes as they type them.
