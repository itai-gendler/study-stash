---
appliesTo:
- type: entity
  id: phone-recording
  effect: changes
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
- unattended: true
---

# Phone recordings change only through the student or the app’s own sending

The student records, names and retries; the app sends waiting recordings when the library can be reached.
