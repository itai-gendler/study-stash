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
- entity: calendar-event
  shows:
  - Title
  - Start
  - End
  - All day
  - Location
  - Class match
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
- entity: edit-draft
  shows:
  - Text
  - Original notes
  - Kept at
- entity: class
  shows:
  - Name
- entity: attachment
  shows:
  - Name
- entity: notes-draft
  shows:
  - Text
  - Writer
  - Created
  - Source attachments
- entity: rewrite
  shows:
  - Engine
  - Progress
  - Started
  - Problem
references:
- kind: code
  role: implementation
  target: engine/src/StudyStash.App/Services/AppHost.Calendar.cs
- kind: code
  role: implementation
  target: engine/src/StudyStash.App/Services/AppHost.cs
- kind: code
  role: implementation
  target: engine/src/StudyStash.App/Services/NoteDrafts.cs
- kind: code
  role: implementation
  target: engine/src/StudyStash.App/Services/NotesDownload.cs
- kind: code
  role: implementation
  target: engine/src/StudyStash.App/Shell.Library.cs
- kind: code
  role: implementation
  target: engine/src/StudyStash.App/Shell.Recording.cs
- kind: code
  role: implementation
  target: engine/src/StudyStash.App/ViewModels/AiNotesModel.cs
- kind: code
  role: implementation
  target: engine/src/StudyStash.App/ViewModels/AttachmentsModel.cs
- kind: code
  role: implementation
  target: engine/src/StudyStash.App/ViewModels/LectureDiagrams.cs
- kind: code
  role: implementation
  target: engine/src/StudyStash.App/ViewModels/LibraryModel.cs
- kind: code
  role: implementation
  target: engine/src/StudyStash.App/ViewModels/TypedNotes.cs
- kind: code
  role: implementation
  target: engine/src/StudyStash.Core/Ai/AiSettings.cs
- kind: code
  role: implementation
  target: engine/src/StudyStash.Core/Ai/DiagramJobs.cs
- kind: code
  role: implementation
  target: engine/src/StudyStash.Core/Ai/Rewrites.cs
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
  target: engine/src/StudyStash.Core/Recording/Recorder.cs
- kind: code
  role: implementation
  target: engine/src/StudyStash.Core/Rich/DiagramSteps.cs
- kind: code
  role: implementation
  target: engine/src/StudyStash.Core/Rich/PlotState.cs
- kind: code
  role: implementation
  target: engine/src/StudyStash.Core/Store.Diagrams.cs
- kind: code
  role: implementation
  target: engine/src/StudyStash.Core/Store.Edits.cs
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
  target: ios/StudyStash/Recording/RecordView.swift
- kind: code
  role: implementation
  target: ios/StudyStash/Screens/Library/LectureView.swift
- kind: code
  role: implementation
  target: web/src/screens/LectureScreen.tsx
---

# Lecture

A lecture’s page: its notes with the student’s own words marked, the transcript, its class and processing state, and the rewrite, edit and filing choices for it.
