---
appliesTo:
- type: entity
  id: recording
- type: entity
  id: phone-recording
- type: entity
  id: lecture
references:
- kind: code
  role: implementation
  target: engine/src/StudyStash.Core/Store.cs
- kind: code
  role: implementation
  target: engine/src/StudyStash.Core/Recording/Recorder.cs
---

# Resending a recording updates the same lecture

Delivery retry and continued recording retain the lecture identity instead of creating a duplicate library entry.
