---
appliesTo:
- type: entity
  id: recording
  effect: creates
references:
- kind: code
  role: implementation
  target: engine/src/StudyStash.Core/Recording/Lectures.cs
- kind: code
  role: implementation
  target: engine/src/StudyStash.Core/Recording/Recorder.cs
permits:
- actors:
  - student
  when:
  - entity: recording-settings
    fact: Role
    is-not: Computer at home
- unattended: true
  when:
  - entity: recording-settings
    fact: Role
    is-not: Computer at home
---

# Recordings are made only on a computer that records

A computer set up only as the library (Computer at home) never records; recordings and imported audio are written down on a computer that records.
