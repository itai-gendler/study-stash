---
kind: primary
routes:
  desktop: Desktop app
  terminal: Terminal
  library-web-library: Library web
steps:
- text: The student asks for a check for a newer release.
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
- text: The Product reports an update when a newer release is found.
  kind: product
  entities:
  - entity: update
    effect: creates
    facts:
    - Version
    - Progress
    - Problem
    to: Available
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

# Check for updates

## Trigger

The student wants to know whether a newer Study Stash is out.

## Outcome

A newer release is shown with its version, ready to install; otherwise this copy is up to date.

## Edge cases

- If checking fails, the current installation keeps working and the check can be tried again.
- An installation that cannot update itself explains how to obtain the new release.
