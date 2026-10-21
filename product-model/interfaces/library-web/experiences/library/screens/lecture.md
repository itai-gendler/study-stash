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
- entity: class
  shows:
  - Name
- entity: attachment
  shows:
  - Name
references:
- kind: code
  role: implementation
  target: engine/src/StudyStash.App/Services/NotesDownload.cs
- kind: code
  role: implementation
  target: engine/src/StudyStash.App/Shell.Library.cs
- kind: code
  role: implementation
  target: engine/src/StudyStash.App/ViewModels/AttachmentsModel.cs
- kind: code
  role: implementation
  target: engine/src/StudyStash.App/ViewModels/LibraryModel.cs
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
  target: engine/src/StudyStash.Library/LibraryWeb.App.cs
- kind: code
  role: implementation
  target: engine/src/StudyStash.Library/LibraryWeb.cs
- kind: code
  role: implementation
  target: ios/StudyStash/Screens/Library/LectureView.swift
- kind: code
  role: implementation
  target: web/src/screens/LectureScreen.tsx
---

# Lecture

A lecture in the library’s web pages: its notes, transcript and class, with Move, Rewrite summary, Download and Delete.
