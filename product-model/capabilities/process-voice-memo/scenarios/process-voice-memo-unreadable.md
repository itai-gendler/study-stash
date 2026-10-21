---
kind: edge
routes:
  phone-web-library: Phone web app
  ios-library: iPhone and iPad app
  desktop: Desktop app
steps:
- text: The capture computer cannot convert the sound file.
  kind: condition
  unattended: true
  entities: []
  contexts: &id001
    phone-web-library:
      place: phone-web::library::voice-memos
    ios-library:
      place: ios::library::voice-memos
    desktop:
      place: desktop
- text: The Product marks the voice memo failed with an explanation.
  kind: product
  entities:
  - entity: voice-memo
    effect: changes
    facts:
    - Problem
    from: Transcribing
    to: Failed
  contexts: *id001
references:
- kind: code
  role: implementation
  target: engine/src/StudyStash.Core/Recording/VoiceMemoImport.cs
- kind: code
  role: implementation
  target: engine/src/StudyStash.Library/VoiceMemos.cs
---

# Keep a failed audio import

## Trigger

The recording computer cannot convert the sound file.

## Outcome

The uploaded original stays available for retry.
