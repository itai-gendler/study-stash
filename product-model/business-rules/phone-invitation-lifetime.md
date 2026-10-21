---
appliesTo:
- type: entity
  id: pairing-code
- type: entity
  id: phone
references:
- kind: code
  role: implementation
  target: engine/src/StudyStash.Library/Devices.cs
---

# A pairing code is temporary and used once

The computer’s latest code lasts ten minutes. A successful pairing consumes it; creating another invitation replaces it.
