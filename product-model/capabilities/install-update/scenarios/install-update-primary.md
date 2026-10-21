---
kind: primary
routes:
  desktop: Desktop app
  terminal: Terminal
  library-web-library: Library web
steps:
- text: The student chooses Update now.
  kind: actor
  actor: student
  entities: []
  contexts: &id001
    desktop:
      place: desktop::updates
    terminal:
      place: terminal
    library-web-library:
      place: library-web::library::updates
- text: The Product starts installing the update.
  kind: product
  entities:
  - entity: update
    effect: changes
    facts:
    - Progress
    from: Available
    to: Installing
  contexts: *id001
  actor: student
- text: The Product completes the update and restarts the app.
  kind: product
  entities:
  - entity: update
    effect: changes
    facts:
    - Progress
    from: Installing
    to: Installed
  contexts: *id001
  actor: student
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
---

# Install update

## Trigger

A newer release is available and the student wants it now.

## Outcome

The new version is downloaded, checked and installed, and Study Stash starts again on it.

## Edge cases

- Automatic installation waits for active, paused and transcribing recording work to be idle.
