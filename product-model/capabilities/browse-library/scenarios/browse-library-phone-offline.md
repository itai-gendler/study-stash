---
kind: edge
routes:
  phone-web-library: Phone web app
  ios-library: iPhone and iPad app
steps:
- text: The student returns to a phone library view while the library is unreachable.
  kind: actor
  actor: student
  entities: []
  contexts: &id001
    phone-web-library:
      place: phone-web::library::home
    ios-library:
      place: ios::library::home
- text: The Product presents the last available lecture and class information.
  kind: product
  entities:
  - entity: lecture
    effect: reads
    facts:
    - Title
    - Class
    - Date
  - entity: class
    effect: reads
    facts:
    - Name
    - Lecture count
  contexts: *id001
  actor: student
references:
- kind: code
  role: implementation
  target: web/src/data/resource.ts
- kind: code
  role: implementation
  target: ios/StudyStash/App/AppModel.swift
---

# Read previously loaded material while away

## Trigger

The student returns to a phone library view while the library is unreachable.

## Outcome

Previously loaded material remains visible with an offline indication; uncached material needs a connection.

## Edge cases

- The web app keeps this visit’s responses in memory; native iOS also retains a local response cache.
