---
appliesTo:
- type: entity
  id: attachment
  effect: creates
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

# Only the student attaches files

Files reach a lecture or class only because the student attached them, from a computer, a phone or a saved notebook.
