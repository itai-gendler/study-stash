---
singleton: true
references:
- kind: code
  role: implementation
  target: engine/src/StudyStash.Core/Config.cs
- kind: code
  role: implementation
  target: engine/src/StudyStash.Library/LibraryWeb.Settings.cs
---

# Library settings

The choices that apply to the shared library.

## Information kept

- **Name** — The library name.
- **Connection password** — The shared password set by the student for connecting clients.
- **Notes enabled** — Whether study notes are generated.
- **AI enabled** — Whether the library’s AI processing is enabled.
- **Filing confidence** — The minimum confidence for automatic class selection.
- **Uses** — School, clubs, work or other supported uses.
- **Automatic updates** — Whether new releases install automatically.
- **Start at login** — Whether the library starts when the person logs in.
