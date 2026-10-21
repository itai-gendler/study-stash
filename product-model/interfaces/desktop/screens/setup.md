---
entities:
- entity: recording-settings
  shows:
  - Model
  - Role
- entity: library-settings
  shows:
  - Name
references:
- kind: code
  role: implementation
  target: engine/src/StudyStash.App/Services/GuidedSetup.cs
- kind: code
  role: implementation
  target: engine/src/StudyStash.App/Services/Setup.cs
- kind: code
  role: implementation
  target: engine/src/StudyStash.App/ViewModels/SetupModel.cs
- kind: code
  role: implementation
  target: engine/src/StudyStash.Library/Cli.cs
---

# Setup

Setup, guided by the student’s AI in a chat or done by hand: the computer’s role, the microphone, the transcription model, the AI, Canvas, classes and starting at login.
