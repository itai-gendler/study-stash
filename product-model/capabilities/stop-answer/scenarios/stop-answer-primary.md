---
kind: primary
routes:
  desktop: desktop
steps:
- text: The student chooses Stop in Ask.
  kind: actor
  actor: student
  entities: []
  contexts: &id001
    desktop:
      place: desktop::ask
- text: The Product stops the question request and retains its partial answer.
  kind: product
  actor: student
  entities:
  - entity: question
    effect: changes
    facts:
    - Answer
    from: Answering
    to: Stopped
  contexts: *id001
references:
- kind: code
  role: implementation
  target: engine/src/StudyStash.App/ViewModels/AiAskModel.cs
---

# Stop answer

## Trigger

The student chooses Stop in Ask.

## Outcome

The request ends and the displayed answer remains available.
