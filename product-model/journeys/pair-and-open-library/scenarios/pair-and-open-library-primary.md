---
kind: primary
result: achieved
routes:
  phone-web: Phone web app
  ios: iPhone and iPad app
steps:
- text: The student types the code shown on the computer into the phone app.
  kind: actor
  actor: student
  entities: []
  contexts:
    phone-web:
      place: phone-web::connection::pair
    ios:
      place: ios::connection::pair
  capability: pair-phone
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
  contexts:
    phone-web:
      place: phone-web::connection::pair
    ios:
      place: ios::connection::pair
  actor: student
  capability: pair-phone
- text: The Product establishes the student’s library access and opens the connected library.
  kind: product
  entities:
  - entity: student
    effect: changes
    facts:
    - Library access
  contexts:
    phone-web:
      place: phone-web::connection::pair
    ios:
      place: ios::connection::pair
  actor: student
  capability: pair-phone
- text: The student requests lectures or searches for a topic.
  kind: actor
  actor: student
  entities:
  - entity: lecture
    effect: reads
    facts: []
  contexts:
    phone-web:
      place: phone-web::library::home
    ios:
      place: ios::library::home
  capability: browse-library
- text: The Product presents class counts and filed lecture matches, newest first.
  kind: product
  entities:
  - entity: class
    effect: reads
    facts:
    - Name
    - Lecture count
    - Group
  - entity: lecture
    effect: reads
    facts:
    - Title
    - Class
    - Date
    - Topics
    - Filed copy
    - Study notes
    - Transcript
  contexts:
    phone-web:
      place: phone-web::library::home
    ios:
      place: ios::library::home
  actor: student
  capability: browse-library
references:
- kind: code
  role: implementation
  target: engine/src/StudyStash.Library/LibraryWeb.Devices.cs
- kind: code
  role: implementation
  target: web/src/screens/Pair.tsx
- kind: code
  role: implementation
  target: ios/StudyStash/App/AppModel.swift
---

# Connect and open the library

## Trigger

The student pairs this device to a library.

## Outcome

The app opens the connected library and presents its filed lectures.
