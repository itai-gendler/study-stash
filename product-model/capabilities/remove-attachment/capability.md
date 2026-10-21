---
availability:
- place: desktop
- place: library-web::library
- place: phone-web::library
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

Delete an attached original and its extracted words from the library.
