---
relations:
- entity: notes-draft
  verb: has
  cardinality: one-to-many
- entity: edit-draft
  verb: has
  cardinality: one-to-many
- entity: attachment
  verb: has
  cardinality: one-to-many
- entity: study-deck
  verb: has
  cardinality: one-to-many
references:
- kind: code
  role: implementation
  target: engine/src/StudyStash.Core/Store.cs
- kind: code
  role: implementation
  target: engine/src/StudyStash.Core/LibraryReader.cs
- kind: code
  role: implementation
  target: engine/src/StudyStash.Core/Pipeline.cs
---

# Lecture

A lecture in the library, with its transcript, the student’s own notes and the study notes written from them. In a folder for a club or work, the same thing is called a meeting.

## Information kept

- **Title** — The current name and the student’s choice to retain it.
- **Class** — The folder where the lecture is filed, including Unsorted.
- **Date** — When the lecture happened.
- **Recorder** — The name attached by its source.
- **Duration** — The known length of the recording.
- **Transcript** — The words received from the recording or import.
- **Your notes** — Original student text received with it.
- **Study notes** — The current write-up, including any rich content and student-word marks.
- **Writer** — The engine that wrote the current notes.
- **Search passages** — Matching excerpts returned by lecture search.
- **Topics** — The topics extracted while filing.
- **Filing choice** — Whether a person or automatic matching selected the class.
- **Problem** — A processing failure, or why existing notes were kept.
- **Filed copy** — Whether the lecture has a filed note available to normal library lists.

## States

### Queued

Accepted for processing; an existing filed copy can still be read.

### Writing

The library is preparing the write-up.

### Filed

Processing has ended, with study notes when they could be written.

### Failed

Filing could not finish.

### Deleted

The lecture has been removed from the active library and may still be restored.
