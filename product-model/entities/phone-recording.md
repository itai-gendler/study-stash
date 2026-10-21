---
relations:
- entity: lecture
  verb: becomes
  cardinality: one-to-one
references:
- kind: code
  role: implementation
  target: ios/StudyStash/Recording/Recording.swift
- kind: code
  role: implementation
  target: ios/StudyStash/Recording/Recorder.swift
---

# Phone recording

A lecture recorded or imported on iPhone or iPad and transcribed on that device.

## Information kept

- **Title** — The recording name and whether the student supplied it.
- **Class** — The class chosen for the recording.
- **Started** — Its local start date and time.
- **Duration** — The recorded duration.
- **Audio** — The local sound file and whether an original is retained.
- **Transcript** — Timed words and the speech language.
- **Your notes** — Text typed during the recording.
- **Problem** — Why a recording could not be sent.

## States

### Recording

The device is capturing the lecture; it may be paused.

### Waiting

Capture has ended and delivery is pending.

### Sending

The device is contacting the library.

### Sent

The library accepted the lecture.

### Failed

Delivery needs attention, including a recording with no recognized words.
