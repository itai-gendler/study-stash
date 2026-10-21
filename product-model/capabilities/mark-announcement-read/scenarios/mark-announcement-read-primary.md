---
kind: primary
routes:
  desktop: Desktop app
steps:
- text: The student opens a new announcement.
  kind: actor
  actor: student
  entities:
  - entity: announcement
    effect: reads
    facts: []
  contexts: &id001
    desktop:
      place: desktop::class
- text: The Product marks the announcement read.
  kind: product
  entities:
  - entity: announcement
    effect: changes
    facts:
    - New
  contexts: *id001
  actor: student
references:
- kind: code
  role: implementation
  target: engine/src/StudyStash.App/ViewModels/CanvasClassModel.cs
- kind: code
  role: implementation
  target: engine/src/StudyStash.Library/LibraryWeb.Canvas.cs
---

# Mark announcement read

## Trigger

A class has a Canvas announcement the student has not read in Study Stash.

## Outcome

The announcement no longer shows as new.
