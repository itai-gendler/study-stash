---
references:
- kind: code
  role: implementation
  target: engine/src/StudyStash.Core/Attachments.cs
- kind: code
  role: implementation
  target: engine/src/StudyStash.Core/Store.Attachments.cs
- kind: code
  role: implementation
  target: engine/src/StudyStash.Library/LibraryWeb.Attachments.cs
---

# Attachment

An original file attached to a lecture or class, with locally extracted words available for notes and questions.

## Information kept

- **Name** — The original recognizable file name.
- **Kind** — The detected file type and its use as notes, slides or a handout.
- **Size** — The size of the original file.
- **Added** — When it was attached.
- **Text** — The words extracted on the library computer.
- **Used in notes** — Whether its text contributed to the current lecture write-up.

## States

### Reading

The original is saved and its text is being extracted.

### Read

Extracted text is available.

### Unread

The original remains available, but no text could be extracted.
