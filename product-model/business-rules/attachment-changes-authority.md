---
appliesTo:
- type: entity
  id: attachment
  effect: changes
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
- unattended: true
---

# Attachments change only by the student’s filing or by the library reading their words

Reading an attachment’s words happens on the library’s computer; moving its lecture or renaming its class moves it with them.
