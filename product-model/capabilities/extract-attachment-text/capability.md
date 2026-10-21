---
availability:
- place: desktop
- place: library-web::library
- place: phone-web::library
- place: ios::library
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

Extract document text and handwriting on the library computer for notes, Ask and AI tools.
