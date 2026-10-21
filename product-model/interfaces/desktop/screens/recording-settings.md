---
entities:
- entity: recording-settings
  shows:
  - Model
  - Language
  - Computer audio
  - Speakers
  - Transcription timing
  - Audio retention
  collects:
  - Model
  - Language
  - Computer audio
  - Speakers
  - Transcription timing
  - Audio retention
references:
- kind: code
  role: implementation
  target: engine/src/StudyStash.App/Services/AppHost.cs
- kind: code
  role: implementation
  target: engine/src/StudyStash.App/Services/ModelSetting.cs
- kind: code
  role: implementation
  target: engine/src/StudyStash.App/Services/Settings.cs
---

# Recording settings

Recording settings: the transcription model and language, when transcription happens, computer audio, telling speakers apart and how long audio is kept.
