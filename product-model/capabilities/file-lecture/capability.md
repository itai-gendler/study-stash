---
availability:
- place: desktop
- place: library-web::library
- place: phone-web::library
- place: ios::library
references:
- kind: code
  role: implementation
  target: engine/src/StudyStash.Core/Pipeline.cs
- kind: code
  role: implementation
  target: engine/src/StudyStash.Core/Classify.cs
- kind: code
  role: implementation
  target: engine/src/StudyStash.Core/Store.cs
- kind: code
  role: implementation
  target: engine/src/StudyStash.Core/Summarize.cs
---

# Write and file lecture

Turn queued material into study notes and file it under a class or Unsorted. The selected AI is called by the library.
