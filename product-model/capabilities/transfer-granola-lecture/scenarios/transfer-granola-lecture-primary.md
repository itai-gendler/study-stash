---
kind: primary
routes:
  desktop: Desktop app
steps:
- text: The student chooses Transfer on an offered Granola lecture.
  kind: actor
  actor: student
  entities:
  - entity: granola-lecture
    effect: reads
    facts: []
  contexts: &id001
    desktop:
      place: desktop::granola
- text: The Product queues the imported lecture and marks the Granola lecture transferred.
  kind: product
  entities:
  - entity: lecture
    effect: creates
    facts:
    - Title
    - Class
    - Date
    - Recorder
    - Duration
    - Transcript
    - Your notes
    - Study notes
    - Writer
    - Topics
    - Filing choice
    - Problem
    - Filed copy
    to: Queued
  - entity: granola-lecture
    effect: changes
    facts:
    - Material
    from: Offered
    to: Transferred
  contexts: *id001
  actor: student
references:
- kind: code
  role: implementation
  target: engine/src/StudyStash.Core/GranolaTransfer.cs
---

# Transfer Granola lecture

## Trigger

Granola has a lecture the student wants in Study Stash.

## Outcome

The lecture goes to the library the way a recording does, to be filed under its class and get study notes.

## Edge cases

- If Granola has not written anything yet, the item remains available to try later.
- A failure reaching either service leaves transfer incomplete and reports why.
- A Granola folder is not treated as a Study Stash class.
