---
kind: edge
routes:
  desktop: Desktop app
  library-web-library: Library web
  phone-web-library: Phone web app
  ios-library: iPhone and iPad app
steps:
- text: Extraction finds no words or fails to read the original.
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
- text: The Product leaves the attachment unread.
  kind: product
  entities:
  - entity: attachment
    effect: changes
    facts:
    - Text
    from: Reading
    to: Unread
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

# Keep an original without text

## Trigger

Extraction finds no words or fails to read the original.

## Outcome

The file remains available and reports no extracted words.
