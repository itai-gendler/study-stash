---
kind: primary
routes:
  desktop: Desktop app
  library-web-library: Library web
  phone-web-library: Phone web app
  ios-library: iPhone and iPad app
steps:
- text: The student opens an attached file.
  kind: actor
  actor: student
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
- text: The Product returns the attachment information and requested content.
  kind: product
  entities:
  - entity: attachment
    effect: reads
    facts:
    - Name
    - Kind
    - Size
    - Added
    - Text
    - Used in notes
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
- kind: code
  role: implementation
  target: ios/StudyStash/Screens/Library/ClassView.swift
- kind: code
  role: implementation
  target: engine/src/StudyStash.Core/ClaudeTools.cs
---

# Read attached material

## Trigger

The student opens an attached file.

## Outcome

The original file or available extracted words are presented, including whether reading is still in progress.
