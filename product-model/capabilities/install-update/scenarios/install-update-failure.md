---
kind: edge
routes:
  desktop: Desktop app
steps:
- text: The release cannot be downloaded or installed.
  kind: condition
  unattended: true
  entities: []
  contexts: &id001
    desktop:
      place: desktop::updates
- text: The Product marks the update failed.
  kind: product
  entities:
  - entity: update
    effect: changes
    facts:
    - Problem
    from: Installing
    to: Failed
  contexts: *id001
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
---

# Keep the current version after failure

## Trigger

The release cannot be downloaded or installed.

## Outcome

The existing app remains usable and reports the problem.
