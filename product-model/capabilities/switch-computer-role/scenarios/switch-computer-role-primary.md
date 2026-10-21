---
kind: primary
routes:
  desktop: Desktop app
steps:
- text: The student chooses a new role for this computer in Connection settings.
  kind: actor
  actor: student
  entities: []
  contexts: &id001
    desktop:
      place: desktop::connection
- text: The Product checks the destination and copies the available library material.
  kind: product
  entities:
  - entity: lecture
    effect: reads
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
  - entity: class
    effect: reads
    facts:
    - Name
    - Description
    - Other names
    - Group
    - Canvas course
    - Modules
    - Lecture count
  - entity: attachment
    effect: reads
    facts:
    - Name
    - Kind
    - Size
    - Added
    - Text
    - Used in notes
  - entity: chat
    effect: reads
    facts:
    - Title
    - Scope
    - Messages
    - Engine
    - Updated
  contexts: *id001
  actor: student
- text: The Product changes recording settings to the chosen role.
  kind: product
  entities:
  - entity: recording-settings
    effect: changes
    facts:
    - Role
  - entity: student
    effect: changes
    facts:
    - Library access
  contexts: *id001
  actor: student
references:
- kind: code
  role: implementation
  target: engine/src/StudyStash.App/Services/RoleSwitch.cs
- kind: code
  role: implementation
  target: engine/src/StudyStash.Core/LibraryMove.cs
---

# Change computer role

## Trigger

The student’s set-up changed: a laptop should become the library, or the library should become a laptop.

## Outcome

The computer works in its new role, with the library’s lectures, classes, attachments and chats copied over; nothing is deleted on the other computer.

## Edge cases

- Existing library material is copied rather than removed from the original computer.
- An interrupted copy can be resumed; already copied items are not duplicated.
- The recording connection changes after the required copy succeeds.
