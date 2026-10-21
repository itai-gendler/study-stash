---
kind: primary
routes:
  desktop: Desktop app
steps:
- text: The student changes a formula plot’s slider or view.
  kind: actor
  actor: student
  entities: []
  contexts: &id001
    desktop:
      place: desktop::lecture
- text: The Product presents the lecture’s plot using the chosen values.
  kind: product
  entities:
  - entity: lecture
    effect: reads
    facts:
    - Study notes
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

# Explore a formula plot

## Trigger

The student changes a formula plot’s slider or view.

## Outcome

The graph is recalculated from the formula with its current values, and reset returns to the original values.

## Edge cases

- Predict hides the curve while the student sketches an expectation, then reveals it for comparison.
- A pointer can show a value on the computed curve.
