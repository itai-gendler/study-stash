---
entities:
- entity: pairing-code
  shows:
  - Code
  - Expires
  - Address
- entity: phone
  shows:
  - Name
references:
- kind: code
  role: implementation
  target: engine/src/StudyStash.App/ViewModels/PhonesModel.cs
- kind: code
  role: implementation
  target: engine/src/StudyStash.Library/Devices.cs
- kind: code
  role: implementation
  target: engine/src/StudyStash.Library/LibraryWeb.Devices.cs
- kind: code
  role: implementation
  target: ios/StudyStash/App/AppModel.swift
- kind: code
  role: implementation
  target: web/src/screens/Settings.tsx
---

# Phones

Phones in the library’s web Settings: the paired phones and Add a phone.
