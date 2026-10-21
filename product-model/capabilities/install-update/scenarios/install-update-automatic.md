---
kind: primary
routes:
  desktop: Desktop app
steps:
- text: Automatic updates are enabled and a newer release has been found.
  kind: condition
  unattended: true
  entities: []
  contexts: &id001
    desktop:
      place: desktop::updates
- text: The Product holds the update while capture work is busy.
  kind: product
  entities:
  - entity: update
    effect: changes
    facts: []
    from: Available
    to: Waiting
  contexts: *id001
- text: The Product installs the update once idle.
  kind: product
  entities:
  - entity: update
    effect: changes
    facts:
    - Progress
    from: Waiting
    to: Installing
  contexts: *id001
- text: The Product completes the update and restarts.
  kind: product
  entities:
  - entity: update
    effect: changes
    facts:
    - Progress
    from: Installing
    to: Installed
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

# Install automatically when idle

## Trigger

Automatic updates are enabled and a newer release has been found.

## Outcome

The release waits for recording work to settle and then replaces the installed version.
