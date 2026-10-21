---
kind: primary
routes:
  desktop: Desktop app
steps:
- text: The student points at or clicks a box of a diagram in the notes.
  kind: actor
  actor: student
  entities: []
  contexts: &id001
    desktop:
      place: desktop::lecture
- text: The Product reveals the selected rich content and its lecture source.
  kind: product
  entities:
  - entity: lecture
    effect: reads
    facts:
    - Study notes
    - Transcript
  contexts: *id001
  actor: student
references:
- kind: code
  role: implementation
  target: engine/src/StudyStash.App/ViewModels/LectureDiagrams.cs
- kind: code
  role: implementation
  target: engine/src/StudyStash.Core/Rich/DiagramSteps.cs
- kind: code
  role: implementation
  target: engine/src/StudyStash.Core/Rich/PlotState.cs
---

# Explore diagrams and graphs

## Trigger

The student wants to study a diagram rather than just look at it.

## Outcome

The box and its arrows stand out, with Explain this, Quiz me and Where was this said?, which opens the transcript at the line that says it.

## Edge cases

- Source moments can open the transcript or retained local audio.
- Questions about a selected part are placed into Ask.
