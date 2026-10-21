---
relations:
- entity: lecture
  verb: becomes
  cardinality: one-to-one
references:
- kind: code
  role: implementation
  target: engine/src/StudyStash.Core/Recording/Lectures.cs
- kind: code
  role: implementation
  target: engine/src/StudyStash.Core/Recording/Recorder.cs
---

# Recording

A lecture captured on the desktop, kept locally while its transcript and notes make their way to the library.

## Information kept

- **Title** — The name, including whether it was typed by the student.
- **Class** — The selected class or no class yet.
- **Started** — When the recording began, with the local date.
- **Duration** — How much sound has been recorded.
- **Audio** — The sound kept on the recording computer and whether it remains available.
- **Transcript** — Timed words, language, transcription progress and optional speaker labels.
- **Your notes** — The student’s own text, preserved independently of generated notes.
- **Timing** — Whether transcription happens during recording or after class.
- **Calendar event** — The event this recording is for, when one was matched or selected.
- **Delivery** — The library’s reported progress, filed title and class, or the last problem.

## States

### Planned

An event’s note exists before recording begins.

### Recording

Sound is being captured.

### Paused

Capture is paused.

### Transcribing

Capture has ended and the remaining sound awaits transcription.

### Sending

The transcript waits to reach the library.

### Writing

The library has accepted it and its processing is being followed.

### Filed

The library has finished processing it.

### Failed

Processing on the recording computer needs attention.
