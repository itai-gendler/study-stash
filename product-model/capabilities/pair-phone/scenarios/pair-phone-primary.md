---
kind: primary
routes:
  phone-web-connection: Phone web app
  ios-connection: iPhone and iPad app
steps:
- text: The student types the code shown on the computer into the phone app.
  kind: actor
  actor: student
  entities: []
  contexts: &id001
    phone-web-connection:
      place: phone-web::connection::pair
    ios-connection:
      place: ios::connection::pair
- text: The Product consumes the supplied pairing code and remembers the named phone.
  kind: product
  entities:
  - entity: pairing-code
    effect: removes
  - entity: phone
    effect: creates
    facts:
    - Name
    - Paired at
    - Last used
  contexts: *id001
  actor: student
- text: The Product establishes the student’s library access.
  kind: product
  entities:
  - entity: student
    effect: changes
    facts:
    - Library access
  contexts: *id001
  actor: student
references:
- kind: code
  role: implementation
  target: web/src/screens/Pair.tsx
- kind: code
  role: implementation
  target: ios/StudyStash/App/AppModel.swift
- kind: code
  role: implementation
  target: engine/src/StudyStash.Library/LibraryWeb.Devices.cs
---

# Pair phone

## Trigger

The student opens the phone app with a code from Add a phone.

## Outcome

The phone is paired: it is listed on the library’s computer and opens the library.

## Edge cases

- An incorrect, expired or already used code leaves the phone at the connection page.
- The library must be reachable to pair.
