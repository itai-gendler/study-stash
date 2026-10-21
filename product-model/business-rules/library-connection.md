---
appliesTo:
- type: context
  context:
    place: library-web::library
- type: context
  context:
    place: phone-web::library
- type: context
  context:
    place: ios::library
references:
- kind: code
  role: implementation
  target: engine/src/StudyStash.Library/Sessions.cs
- kind: code
  role: implementation
  target: engine/src/StudyStash.Library/Devices.cs
- kind: code
  role: implementation
  target: engine/src/StudyStash.Library/LibraryWeb.cs
---

# The library opens in a browser or on a phone only once it is connected

The library’s web pages open after signing in with the library password, and the phone apps after pairing with a code shown on the computer. Log out ends that browser’s sign-in, a new library password ends every browser sign-in, and a removed phone can no longer read the library from its next request.
