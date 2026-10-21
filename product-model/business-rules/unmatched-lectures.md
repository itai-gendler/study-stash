---
appliesTo:
- type: entity
  id: lecture
- type: entity
  id: library-settings
references:
- kind: code
  role: implementation
  target: engine/src/StudyStash.Core/Classify.cs
---

# An uncertain class match remains Unsorted

A reliable manual, name or alias match takes precedence over AI classification. AI filing below the configured confidence does not choose a class.
