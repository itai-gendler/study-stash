---
availability:
- place: phone-web::library
- place: ios::library
- place: desktop
references:
- kind: code
  role: implementation
  target: engine/src/StudyStash.Core/Recording/VoiceMemoImport.cs
- kind: code
  role: implementation
  target: engine/src/StudyStash.Library/VoiceMemos.cs
---

# Process imported audio

Let a recording computer convert a queued voice memo into its ordinary transcription and delivery queue.
