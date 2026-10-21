---
appliesTo:
- type: entity
  id: recording
- type: entity
  id: phone-recording
- type: entity
  id: voice-memo
references:
- kind: code
  role: implementation
  target: engine/src/StudyStash.Core/Recording/Lectures.cs
- kind: code
  role: implementation
  target: ios/StudyStash/Recording/Recording.swift
---

# Normal recording delivery carries words rather than sound

Desktop and native recording delivery sends recognized speech and personal notes; sound stays on the recording device. Uploaded audio imports are a separate workflow.
