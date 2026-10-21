---
kind: primary
routes:
  desktop: Desktop app
steps:
- text: The student points at a drawing or hides its labels.
  kind: actor
  actor: student
  entities: []
  contexts: &id001
    desktop:
      place: desktop::lecture
- text: The Product presents the lecture’s labeled drawing and its source words.
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

# Study a labeled drawing

## Trigger

The student points at a drawing or hides its labels.

## Outcome

The selected part is highlighted; labels can be restored and the cited source moment can be opened.
