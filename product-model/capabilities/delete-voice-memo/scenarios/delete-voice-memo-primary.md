---
kind: primary
routes:
  phone-web-library: Phone web app
steps:
- text: The student removes a failed audio import.
  kind: actor
  actor: student
  entities: []
  contexts: &id001
    phone-web-library:
      place: phone-web::library::voice-memos
- text: The Product removes the voice memo and uploaded file.
  kind: product
  entities:
  - entity: voice-memo
    effect: removes
    from: Failed
  contexts: *id001
  actor: student
references:
- kind: code
  role: implementation
  target: web/src/screens/VoiceMemo.tsx
- kind: code
  role: implementation
  target: engine/src/StudyStash.Library/LibraryWeb.VoiceMemos.cs
- kind: code
  role: implementation
  target: engine/src/StudyStash.Library/VoiceMemos.cs
---

# Delete imported audio

## Trigger

An imported recording could not become a lecture and is not wanted.

## Outcome

The import and its uploaded audio are removed from the library.

## Edge cases

- The phone presents removal alongside a failed import.
- Removing an import record does not remove a lecture already produced from it.
