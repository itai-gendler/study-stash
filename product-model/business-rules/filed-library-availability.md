---
appliesTo:
- type: entity
  id: lecture
references:
- kind: code
  role: implementation
  target: engine/src/StudyStash.Core/Store.cs
- kind: code
  role: implementation
  target: engine/src/StudyStash.Core/LibraryReader.cs
---

# Normal library lists contain filed lectures

New queued work waits outside the filed list. An already filed lecture remains readable while it is queued for another write-up. The recording page can show progress before filing.
