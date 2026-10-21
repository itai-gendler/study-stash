---
availability:
- place: desktop
- place: library-web::library
- place: phone-web::library
- place: ios::library
references:
- kind: code
  role: implementation
  target: engine/src/StudyStash.App/ViewModels/PhonesModel.cs
- kind: code
  role: implementation
  target: engine/src/StudyStash.Library/LibraryWeb.Devices.cs
- kind: code
  role: implementation
  target: web/src/screens/Settings.tsx
- kind: code
  role: implementation
  target: ios/StudyStash/App/AppModel.swift
domain: phones
---

# Remove phone

Forget a device from the computer, or forget the current library from the phone.
