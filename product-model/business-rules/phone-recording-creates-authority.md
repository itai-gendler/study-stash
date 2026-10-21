---
appliesTo:
- type: entity
  id: phone-recording
  effect: creates
references:
- kind: code
  role: implementation
  target: ios/StudyStash/Recording/Recording.swift
- kind: code
  role: implementation
  target: ios/StudyStash/Recording/Recorder.swift
permits:
- actors:
  - student
---

# Only the student starts or imports a phone recording

Phone recordings come from the student’s Record or from a sound file they import.
