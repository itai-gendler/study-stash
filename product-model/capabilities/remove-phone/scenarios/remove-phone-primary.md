---
kind: primary
routes:
  desktop: Desktop app
  library-web-library: Library web
  phone-web-library: Phone web app
  ios-library: iPhone and iPad app
steps:
- text: The student removes a paired phone on the computer, or chooses Remove this phone on the phone.
  kind: actor
  actor: student
  entities: []
  contexts: &id001
    desktop:
      place: desktop::phones
    library-web-library:
      place: library-web::library::phones
    phone-web-library:
      place: phone-web::library::phones
    ios-library:
      place: ios::library::phones
- text: The Product removes the phone from the paired devices.
  kind: product
  entities:
  - entity: phone
    effect: removes
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
  target: web/src/screens/Settings.tsx
- kind: code
  role: implementation
  target: ios/StudyStash/App/AppModel.swift
---

# Remove phone

## Trigger

A phone should no longer read the library.

## Outcome

The phone is no longer paired and cannot read the library until it is added again.

## Edge cases

- Removing another device takes effect on its next library request.
- Forgetting the library from the phone clears its connection and cached library responses.
