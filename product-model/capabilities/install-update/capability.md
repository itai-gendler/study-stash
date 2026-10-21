---
availability:
- place: desktop
- place: terminal
- place: library-web::library
references:
- kind: code
  role: implementation
  target: engine/src/StudyStash.App/Services/AppUpdates.cs
- kind: code
  role: implementation
  target: engine/src/StudyStash.Core/Updates.cs
- kind: code
  role: implementation
  target: engine/src/StudyStash.Library/Cli.cs
- kind: code
  role: implementation
  target: engine/src/StudyStash.Library/LibraryWeb.cs
domain: library
---

# Install update

Download and install an available Study Stash release, retaining the old copy if installation fails.
