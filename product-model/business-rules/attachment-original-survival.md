---
appliesTo:
- type: entity
  id: attachment
references:
- kind: code
  role: implementation
  target: engine/src/StudyStash.Core/Attachments.cs
- kind: code
  role: implementation
  target: engine/src/StudyStash.Library/LibraryWeb.Attachments.cs
---

# An unreadable attachment retains its original file

Failure to extract text does not remove the original. Ask and future write-ups can use extracted words only once they are available.
