---
singleton: true
references:
- kind: code
  role: implementation
  target: engine/src/StudyStash.App/Services/AppHost.cs
- kind: code
  role: implementation
  target: engine/src/StudyStash.App/Services/Settings.cs
---

# Recording settings

The choices kept on a recording computer.

## Information kept

- **Model** — The transcription model selected and downloaded.
- **Language** — The speech language or automatic detection.
- **Computer audio** — Whether computer sound is included.
- **Speakers** — Whether voices are labeled.
- **Transcription timing** — During the lecture or after class.
- **Audio retention** — How long filed audio is kept.
- **Role** — What this computer is for: Just this computer (records and keeps the library), Laptop for class (records and sends lectures to the library) or Computer at home (keeps and writes up lectures, and does not record).
