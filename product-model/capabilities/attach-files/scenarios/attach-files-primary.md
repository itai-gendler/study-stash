---
kind: primary
routes:
  desktop: Desktop app
  library-web-library: Library web
  phone-web-library: Phone web app
  ios-library: iPhone and iPad app
steps:
- text: The student drops or picks photos, handwriting, PDFs or slides for a lecture or class.
  kind: actor
  actor: student
  entities:
  - entity: class
    effect: reads
    facts: []
  - entity: lecture
    effect: reads
    facts: []
  contexts:
    desktop:
      place: desktop::attachments
    library-web-library:
      place: library-web::library::attachments
    phone-web-library:
      place: phone-web::library::attachments
    ios-library:
      place: ios::library::attachments
- text: The Product saves each attachment and queues its text for reading.
  kind: product
  entities:
  - entity: attachment
    effect: creates
    facts:
    - Name
    - Kind
    - Size
    - Added
    - Text
    - Used in notes
    to: Reading
  contexts:
    desktop:
      place: desktop::attachments
    library-web-library:
      place: library-web::library::attachments
    phone-web-library:
      place: phone-web::library::attachments
    ios-library:
      place: ios::library::attachments
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
  target: web/src/screens/Upload.tsx
- kind: code
  role: implementation
  target: ios/StudyStash/Screens/Add/AddFilesView.swift
- kind: code
  role: implementation
  target: engine/src/StudyStash.Core/Attachments.cs
---

# Attach files

## Trigger

The student has their own notes, slides or a handout that belong with a lecture or class.

## Outcome

Each file is kept with its lecture or class, and its words are read on the library’s computer for the notes, Ask and AI apps.

## Edge cases

- An upload is limited to 200 MB in total; an oversized request or empty file is refused before any files from that request are kept.
- Files can be attached to Unsorted when no class or lecture is selected.
- A name already used in the destination gets a numbered file name.
