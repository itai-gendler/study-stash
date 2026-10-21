---
kind: primary
routes:
  desktop: Desktop app
steps:
- text: The student changes the transcription model, language, timing, computer audio, Tell speakers apart or how long audio is kept.
  kind: actor
  actor: student
  entities:
  - entity: recording-settings
    effect: reads
    facts: []
  contexts: &id001
    desktop:
      place: desktop::recording-settings
- text: The Product keeps the recording settings for subsequent capture and transcription.
  kind: product
  entities:
  - entity: recording-settings
    effect: changes
    facts:
    - Model
    - Language
    - Computer audio
    - Speakers
    - Transcription timing
    - Audio retention
  contexts: *id001
  actor: student
references:
- kind: code
  role: implementation
  target: engine/src/StudyStash.App/Services/Settings.cs
- kind: code
  role: implementation
  target: engine/src/StudyStash.App/Services/ModelSetting.cs
- kind: code
  role: implementation
  target: engine/src/StudyStash.App/Services/AppHost.cs
---

# Change recording settings

## Trigger

The student wants recording and transcription to work differently on this computer.

## Outcome

The next recordings are captured and transcribed with the new choices.

## Edge cases

- Model selection downloads missing model files and reports download or load failure.
- After-class timing delays transcription while a capture remains active, including when paused.
