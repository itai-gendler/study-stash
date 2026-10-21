---
appliesTo:
- type: entity
  id: recording-settings
- type: entity
  id: lecture
references:
- kind: code
  role: implementation
  target: engine/src/StudyStash.App/Services/RoleSwitch.cs
- kind: code
  role: implementation
  target: engine/src/StudyStash.Core/LibraryMove.cs
---

# Changing library computers preserves the source library

Role switching copies existing material and can resume a partial transfer. The old library remains intact.
