---
kind: primary
routes:
  phone-web-library: Phone web app
steps:
- text: The student chooses Try again on a failed audio import.
  kind: actor
  actor: student
  entities: []
  contexts: &id001
    phone-web-library:
      place: phone-web::library::voice-memos
- text: The Product clears the voice memo problem and makes it available again.
  kind: product
  entities:
  - entity: voice-memo
    effect: changes
    facts:
    - Problem
    from: Failed
    to: Waiting
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

# Try imported audio again

## Trigger

An imported recording failed to become a lecture.

## Outcome

The import waits again for a recording computer.
