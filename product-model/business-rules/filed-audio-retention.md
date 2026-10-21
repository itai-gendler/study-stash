---
appliesTo:
- type: entity
  id: recording
- type: entity
  id: recording-settings
references:
- kind: code
  role: implementation
  target: engine/src/StudyStash.Core/Recording/Recorder.cs
---

# Audio retention applies after a desktop recording is filed

Pruning removes eligible local sound according to the selected retention period while retaining the transcript. Unfinished delivery retains its sound.
