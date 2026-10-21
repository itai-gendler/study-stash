---
kind: primary
routes:
  desktop: Desktop app
steps:
- text: Every five minutes, the Product looks at the connected Granola for lectures it has not brought over or been told to leave.
  kind: condition
  unattended: true
  entities:
  - entity: lecture
    effect: reads
    facts: []
  - entity: granola-connection
    effect: reads
    facts:
    - Connected
  contexts:
    desktop:
      place: desktop
- text: The Product offers each new Granola lecture once Granola has written its notes or it started more than three hours ago, announcing it once with Transfer when notifications are on.
  kind: product
  entities:
  - entity: granola-lecture
    effect: creates
    to: Offered
    facts:
    - Title
    - Date
    - Material
  - entity: granola-connection
    effect: reads
    facts:
    - Notifications
  contexts:
    desktop:
      place: desktop
references:
- kind: code
  role: implementation
  target: engine/src/StudyStash.Core/GranolaTransfer.cs
---

# Offer a new Granola lecture

## Trigger

The regular look at Granola finds a lecture Study Stash does not have.

## Outcome

The lecture is offered for transfer, in a notification and on the Granola settings page.

## Edge cases

- A lecture still being recorded in Granola waits until its notes are written or three hours have passed.
- A lecture the library already has, brought over from another computer, is remembered as transferred and not offered.
- A free Granola plan lists the last 30 days of lectures.
