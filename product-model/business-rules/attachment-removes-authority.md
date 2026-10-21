---
appliesTo:
- type: entity
  id: attachment
  effect: removes
references:
- kind: code
  role: implementation
  target: engine/src/StudyStash.Core/Attachments.cs
- kind: code
  role: implementation
  target: engine/src/StudyStash.Core/Store.Attachments.cs
- kind: code
  role: implementation
  target: engine/src/StudyStash.Library/LibraryWeb.Attachments.cs
permits:
- actors:
  - student
---

# Only the student removes an attachment

Removing an attachment deletes the file and the words read from it.
