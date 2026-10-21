---
kind: primary
routes:
  desktop: Desktop app
  library-web-library: Library web
steps:
- text: The student chooses Add a phone.
  kind: actor
  actor: student
  entities: []
  contexts: &id001
    desktop:
      place: desktop::phones
    library-web-library:
      place: library-web::library::phones
- text: The Product creates a pairing code and shows its expiry and phone address.
  kind: product
  entities:
  - entity: pairing-code
    effect: creates
    facts:
    - Code
    - Expires
    - Address
  contexts: *id001
  actor: student
references:
- kind: code
  role: implementation
  target: engine/src/StudyStash.App/ViewModels/PhonesModel.cs
- kind: code
  role: implementation
  target: engine/src/StudyStash.Library/LibraryWeb.Devices.cs
- kind: code
  role: implementation
  target: engine/src/StudyStash.Library/Devices.cs
---

# Add a phone

## Trigger

The student wants to read their library on a phone or tablet.

## Outcome

A six-digit code is shown with the address to open on the phone; it works once, for ten minutes.

## Edge cases

- The code lasts ten minutes and is used once.
- Asking for a new code replaces the previous invitation.
