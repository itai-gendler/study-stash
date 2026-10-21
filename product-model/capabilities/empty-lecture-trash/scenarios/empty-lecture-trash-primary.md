---
kind: primary
routes:
  desktop: Desktop app
steps:
- text: The library cleans trash older than ten minutes.
  kind: condition
  unattended: true
  entities: []
  contexts: &id001
    desktop:
      place: desktop::home
- text: The Product removes the expired deleted lecture.
  kind: product
  entities:
  - entity: lecture
    effect: removes
    from: Deleted
  contexts: *id001
references:
- kind: code
  role: implementation
  target: engine/src/StudyStash.Core/Store.cs
- kind: code
  role: implementation
  target: engine/src/StudyStash.Library/LibraryWeb.App.cs
---

# Expire deleted lectures

## Trigger

The library cleans trash older than ten minutes.

## Outcome

The expired lecture cannot be restored; connected desktops learn that their corresponding local copy can go.


## Edge cases

- Library startup empties any trash left by the previous run.
