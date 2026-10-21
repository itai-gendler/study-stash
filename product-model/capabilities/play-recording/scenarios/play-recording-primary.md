---
kind: primary
routes:
  desktop: Desktop app
steps:
- text: The student plays the recording, or a moment from its transcript or a diagram.
  kind: actor
  actor: student
  entities:
  - entity: recording
    effect: reads
    facts: []
  contexts: &id001
    desktop:
      place: desktop::lecture
- text: The Product reads the recording audio and starts at the chosen moment.
  kind: product
  entities:
  - entity: recording
    effect: reads
    facts:
    - Audio
    - Transcript
  contexts: *id001
  actor: student
references:
- kind: code
  role: implementation
  target: engine/src/StudyStash.App/ViewModels/LectureDiagrams.cs
- kind: code
  role: implementation
  target: engine/src/StudyStash.App/Shell.Library.cs
---

# Play recording

## Trigger

The student wants to hear part of the lecture again.

## Outcome

The sound kept on this computer plays from the chosen moment.

## Edge cases

- When the local sound is no longer present, the transcript remains available and sound playback is unavailable.
