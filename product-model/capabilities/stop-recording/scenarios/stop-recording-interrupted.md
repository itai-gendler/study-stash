---
kind: edge
routes:
  desktop: Desktop app
steps:
- text: The desktop app starts and finds a recording still marked as recording, because the app quit or the computer stopped while it recorded.
  kind: condition
  unattended: true
  entities:
  - entity: recording
    effect: reads
    facts:
    - Audio
  contexts:
    desktop:
      place: desktop::recording
- text: The Product closes off the sound saved so far, so that it can be read.
  kind: product
  entities:
  - entity: recording
    effect: changes
    facts:
    - Audio
  contexts:
    desktop:
      place: desktop::recording
- text: The Product stops the recording at the length that sound reaches and queues it for transcription, keeping its title and typed notes as they were.
  kind: product
  entities:
  - entity: recording
    effect: changes
    from: Recording
    to: Transcribing
    facts:
    - Duration
  contexts:
    desktop:
      place: desktop::recording
references:
- kind: code
  role: implementation
  target: engine/src/StudyStash.Core/Recording/Recorder.cs
---

# Recover a recording cut short

## Trigger

The desktop app starts again after it quit or the computer stopped while a lecture was recording.

## Outcome

What was recorded before the interruption is kept and goes on to be transcribed, sent and filed like any stopped recording.

## Edge cases

- A recording left paused is recovered the same way.
- A recording whose sound cannot be opened is marked Failed with its problem, for Try again, and the app still starts.
- A recording with no sound and no words yet is let go.
