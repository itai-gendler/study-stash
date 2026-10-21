---
kind: primary
routes:
  desktop: Desktop app
  terminal: Terminal
steps:
- text: The student says which AI they have and works through setup, guided by their AI or by hand.
  kind: actor
  actor: student
  entities: []
  contexts: &id001
    desktop:
      place: desktop::setup
    terminal:
      place: terminal
- text: The Product saves recording settings and library settings for the chosen role.
  kind: product
  entities:
  - entity: recording-settings
    effect: changes
    facts:
    - Role
    - Model
  - entity: library-settings
    effect: changes
    facts:
    - Name
  contexts: *id001
  actor: student
- text: The Product keeps the student’s name and library connection.
  kind: product
  entities:
  - entity: student
    effect: changes
    facts:
    - Display name
    - Library access
  contexts: *id001
  actor: student
references:
- kind: code
  role: implementation
  target: engine/src/StudyStash.App/Services/Setup.cs
- kind: code
  role: implementation
  target: engine/src/StudyStash.App/Services/GuidedSetup.cs
- kind: code
  role: implementation
  target: engine/src/StudyStash.App/ViewModels/SetupModel.cs
- kind: code
  role: implementation
  target: engine/src/StudyStash.Library/Cli.cs
---

# Set up Study Stash

## Trigger

Study Stash opens for the first time, or the student chooses Run setup.

## Outcome

This computer has its role, its transcription model and a library to keep its lectures.

## Edge cases

- Guided setup uses the selected external AI plan; provider sign-in takes place with that provider.
- Setup can finish without AI note generation.
- Required downloads report progress and can be tried again after failure.
