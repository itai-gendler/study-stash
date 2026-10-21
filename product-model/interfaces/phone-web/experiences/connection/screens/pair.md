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
  - Paired at
  - Last used
references:
- kind: code
  role: implementation
  target: engine/src/StudyStash.Library/LibraryWeb.Devices.cs
- kind: code
  role: implementation
  target: ios/StudyStash/App/AppModel.swift
- kind: code
  role: implementation
  target: web/src/screens/Pair.tsx
---

# Pair

Where the phone web app first asks for the code shown on the computer, to connect to the library.
