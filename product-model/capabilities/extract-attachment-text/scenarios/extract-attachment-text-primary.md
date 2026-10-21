---
kind: primary
routes:
  desktop: Desktop app
  library-web-library: Library web
  phone-web-library: Phone web app
  ios-library: iPhone and iPad app
steps:
- text: An attached original is waiting for text extraction.
  kind: condition
  unattended: true
  entities: []
  contexts: &id001
    desktop:
      place: desktop::attachments
    library-web-library:
      place: library-web::library::attachments
    phone-web-library:
      place: phone-web::library::attachments
    ios-library:
      place: ios::library::attachments
- text: The Product reads and stores the attachment text.
  kind: product
  entities:
  - entity: attachment
    effect: changes
    facts:
    - Text
    from: Reading
    to: Read
  contexts: *id001
references:
- kind: code
  role: implementation
  target: engine/src/StudyStash.Library/LibraryWeb.Attachments.cs
- kind: code
  role: implementation
  target: engine/src/StudyStash.Core/Attachments.cs
- kind: code
  role: implementation
  target: engine/src/StudyStash.Core/Store.Attachments.cs
---

# Read words from attachments

## Trigger

An attached original is waiting for text extraction.

## Outcome

Its words become available for questions and future write-ups.
