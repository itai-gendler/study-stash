---
entities:
- entity: question
  shows:
  - Question
  - Scope
  - Answer
  - Sources
  - Engine
- entity: lecture
  shows:
  - Title
  - Class
  - Transcript
  - Study notes
- entity: attachment
  shows:
  - Text
- entity: class
  shows:
  - Name
references:
- kind: code
  role: implementation
  target: engine/src/StudyStash.App/ViewModels/AiAskModel.cs
- kind: code
  role: implementation
  target: engine/src/StudyStash.Core/Ai/AiJobs.cs
- kind: code
  role: implementation
  target: engine/src/StudyStash.Core/LibraryReader.cs
- kind: code
  role: implementation
  target: ios/StudyStash/Screens/Ask/AskViews.swift
- kind: code
  role: implementation
  target: web/src/screens/Ask.tsx
---

# Ask

The Ask bar and quick panel answers: a question about a lecture, a class or all of them, its streamed answer, the engine that gave it and the material it drew on.
