---
references:
- kind: code
  role: implementation
  target: engine/src/StudyStash.Library/VoiceMemos.cs
- kind: code
  role: implementation
  target: engine/src/StudyStash.Core/Recording/VoiceMemoImport.cs
---

# Voice memo

An audio file sent to the library from the phone web app, or from the iPhone or iPad app when it cannot recognise the speech itself, waiting for a computer that records to turn it into a lecture.

## Information kept

- **Name** — The uploaded audio file name.
- **Title** — The supplied title or file name.
- **Class** — The selected class or none.
- **Added** — When the audio arrived.
- **Size** — The size of the uploaded recording.
- **Computer** — The recording computer processing it.
- **Lecture** — The resulting lecture, when imported.
- **Problem** — Why import failed.

## States

### Waiting

Waiting for a recording computer.

### Transcribing

A computer has claimed the audio for import.

### Done

The audio has become a local recording for transcription and delivery.

### Failed

Import needs attention.
