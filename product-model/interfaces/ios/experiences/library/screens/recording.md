---
entities:
- entity: phone-recording
  shows:
  - Title
  - Class
  - Started
  - Duration
  - Audio
  - Transcript
  - Your notes
  - Problem
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

The recorder on iPhone and iPad: the recording’s name and class, Pause and Stop, the words recognised on the device, the student’s notes, and recordings waiting to send.
