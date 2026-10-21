---
kind: primary
routes:
  desktop: Desktop app
  library-web-library: Library web
  phone-web-library: Phone web app
steps:
- text: The student removes an attached file.
  kind: actor
  actor: student
  entities:
  - entity: attachment
    effect: reads
    facts: []
  contexts: &id001
    desktop:
      place: desktop::attachments
    library-web-library:
      place: library-web::library::attachments
    phone-web-library:
      place: phone-web::library::attachments
- text: The Product removes the attachment and its file.
  kind: product
  entities:
  - entity: attachment
    effect: removes
    from: Read
  contexts: *id001
  actor: student
references:
- kind: code
  role: implementation
  target: engine/src/StudyStash.App/ViewModels/AttachmentsModel.cs
- kind: code
  role: implementation
  target: engine/src/StudyStash.Library/LibraryWeb.Attachments.cs
- kind: code
  role: implementation
  target: web/src/screens/attachments.tsx
---

# Remove attachment

## Trigger

A file attached to a lecture or class is no longer wanted.

## Outcome

The file and the words read from it are gone from the library at once.

## Edge cases

- Attachment deletion is immediate and has no lecture-style Undo.
