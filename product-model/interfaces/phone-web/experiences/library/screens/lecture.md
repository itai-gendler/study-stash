---
entities:
- entity: lecture
  shows:
  - Title
  - Class
  - Date
  - Duration
  - Transcript
  - Your notes
  - Study notes
  - Writer
  - Topics
  - Filing choice
  - Problem
  - Filed copy
references:
- kind: code
  role: implementation
  target: engine/src/StudyStash.App/Shell.Library.cs
- kind: code
  role: implementation
  target: engine/src/StudyStash.Core/Ai/AiSettings.cs
- kind: code
  role: implementation
  target: engine/src/StudyStash.Core/Ai/DiagramJobs.cs
- kind: code
  role: implementation
  target: engine/src/StudyStash.Core/Classify.cs
- kind: code
  role: implementation
  target: engine/src/StudyStash.Core/ClaudeTools.cs
- kind: code
  role: implementation
  target: engine/src/StudyStash.Core/LibraryReader.cs
- kind: code
  role: implementation
  target: engine/src/StudyStash.Core/Pipeline.cs
- kind: code
  role: implementation
  target: engine/src/StudyStash.Core/Store.Diagrams.cs
- kind: code
  role: implementation
  target: engine/src/StudyStash.Core/Store.cs
- kind: code
  role: implementation
  target: engine/src/StudyStash.Core/Summarize.cs
- kind: code
  role: implementation
  target: ios/StudyStash/Screens/Library/LectureView.swift
- kind: code
  role: implementation
  target: web/src/screens/LectureScreen.tsx
---

# Lecture

A lecture in the phone web app: its notes, transcript and class.
