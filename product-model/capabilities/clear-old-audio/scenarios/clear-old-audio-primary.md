---
kind: primary
routes:
  desktop: Desktop app
steps:
- text: Filed local audio reaches the configured retention age.
  kind: condition
  unattended: true
  entities: []
  contexts: &id001
    desktop:
      place: desktop::recording
- text: The Product clears the recording audio while preserving its transcript.
  kind: product
  entities:
  - entity: recording
    effect: changes
    facts:
    - Audio
  contexts: *id001
references:
- kind: code
  role: implementation
  target: engine/src/StudyStash.App/Services/AppHost.cs
- kind: code
  role: implementation
  target: engine/src/StudyStash.Core/Recording/Lectures.cs
---

# Clear old audio

## Trigger

Filed local audio reaches the configured retention age.

## Outcome

The recording’s text remains and the old audio no longer occupies space.
