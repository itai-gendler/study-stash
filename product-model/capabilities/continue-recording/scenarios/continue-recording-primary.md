---
kind: primary
routes:
  desktop: Desktop app
steps:
- text: The student chooses Keep recording on a recording stopped earlier.
  kind: actor
  actor: student
  entities:
  - entity: recording
    effect: reads
    facts: []
  contexts: &id001
    desktop:
      place: desktop::lecture
- text: The Product reopens the recording and retains the earlier words.
  kind: product
  entities:
  - entity: recording
    effect: changes
    facts:
    - Audio
    - Title
    - Transcript
    - Your notes
    from: Filed
    to: Recording
  contexts: *id001
  actor: student
references:
- kind: code
  role: implementation
  target: engine/src/StudyStash.Core/Recording/Recorder.cs
- kind: code
  role: implementation
  target: engine/src/StudyStash.App/Services/AppHost.cs
- kind: code
  role: implementation
  target: engine/src/StudyStash.App/Shell.Library.cs
---

# Keep recording

## Trigger

More of the same lecture needs recording after it was stopped.

## Outcome

New sound is added to the same recording, after its earlier words, under the same name.

## Edge cases

- If retained audio has expired, the new sound begins after the earlier transcript.
- A continuation shorter than five seconds leaves the prior processing state as it was.
- A session already capturing sound must be stopped before a different one starts.
